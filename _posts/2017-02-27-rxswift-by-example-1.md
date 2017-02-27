---
layout: post
title:  "RxSwift by examples #1 - The basics"
date:   2017-02-27 23:30:00 +1100
categories: [Swift]
tags: [ios, swift, reactiveX, rxswift]

---

# [RxSwift by examples #1 - The basics.](https://www.thedroidsonroids.com/blog/ios/rxswift-by-examples-1-the-basics/)


## ReativeX

* Observer pattern
* Iterator pattern
* functional programming


## Why?

* Multi-Threading environment
* Data Algorithm focus


## Definitions

* `smartphone` is an **`observable`**
* **`emits signals`** like Facebook notifications, messages and so on.
* `You` are naturally **`subscribed`** / **`observer`**


## Example

### Install

* [CocoapPods](https://guides.cocoapods.org/using/using-cocoapods.html)

**Tested with `pod --version`: `1.1.1`**

	# Podfile
	use_frameworks!

	target 'YOUR_TARGET_NAME' do
	    pod 'RxSwift',    '~> 3.0'
	    pod 'RxCocoa',    '~> 3.0'
	end

	# RxTests and RxBlocking make the most sense in the context of unit/integration tests
	target 'YOUR_TESTING_TARGET' do
	    pod 'RxBlocking', '~> 3.0'
	    pod 'RxTest',     '~> 3.0'
	end
---
	$ pod install

* [Carthage](https://github.com/Carthage/Carthage)

**Tested with `carthage version`: `0.18.1`**

Add this to `Cartfile`

	github "ReactiveX/RxSwift" ~> 3.0
---
	$ carthage update

* [Swift Package Manager](https://github.com/apple/swift-package-manager)

**Tested with `swift build --version`: `3.0.0 (swiftpm-19)`**

Create a `Package.swift` file.
	
	import PackageDescription
	
	let package = Package(
	    name: "RxTestProject",
	    targets: [],
	    dependencies: [
	        .Package(url: "https://github.com/ReactiveX/RxSwift.git", majorVersion: 3)
	    ]
	)
---
	$ swift build

### Import

	import RxCocoa
	import RxSwift

### Observe SearchBar

    searchBar.rx.text // Observable property thanks to RxCocoa
	    .orEmpty // Make it non-optional
	    .subscribe(onNext: { [unowned self] query in // Here we subscribe to every new value, that is not empty (thanks to filter above).
	        self.shownCities = self.allCities.filter { $0.hasPrefix(query) } // We now do our "API Request" to find cities.
	        self.tableView.reloadData() // And reload table view data.
    })
	    .addDisposableTo(disposeBag)
    
### Protecting API backend

    .debounce(0.5, scheduler: MainScheduler.instance) // Wait 0.5 for changes.
    .distinctUntilChanged() // If they didn't occur, check if the new value is the same as old.
    .filter { !$0.isEmpty } // If the new value is really new, filter for non-empty query.


## Notes

* `[unowned self]`: closure에 진입할 때 self가 살아있다는 것이 보장된 상태일 때 사용
* `DisposeBag`: observer의 연결 해제?를 담당