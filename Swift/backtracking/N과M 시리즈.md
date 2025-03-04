# 15649. N과M(1)
```swift
var arr = Array(repeating:0, count: 10)
var isused = Array(repeating:false, count: 10)
var nm = readLine()!.split(separator: " ").map{Int($0)!}
let n = nm[0]; let m = nm[1]
backtracking(0)

func backtracking(_ k:Int) {
    if k == m {
        for i in 0..<m {
            print(arr[i], terminator: " ")
        }
        print()
        return
    }
    for i in 1..<n+1 {
        if !isused[i] {
            arr[k] = i
            isused[i] = true
            backtracking(k+1)
            isused[i] = false
        }
    }
}
```
# 15650. N과M(2)
```swift
let nm = readLine()!.split(separator:" ").map{Int($0)!}
let(n,m) = (nm[0],nm[1])
var arr = Array(repeating:0, count: m+1)
var vis = Array(repeating:false, count: n+1)
solve(0, 1)

func solve (_ k:Int, _ cur: Int) {
    var cur = cur
    
    if k == m {
        for i in 0..<m{
            print(arr[i], terminator: " ")
        }
        print()
        return
    }
    if k != 0 { cur  = arr[k-1]}
    for i in cur...n {
        if !vis[i] {
            arr[k] = i
            vis[i] = true
            solve(k+1, cur)
            vis[i] = false
            
        }
    }
}
```
# 15651. N과M(3) 
```swift
let nm = readLine()!.split(separator: " ").map { Int($0)! }
let (n, m) = (nm[0], nm[1])
var arr = Array(repeating: 0, count: m)
var result = ""

func solve(_ k: Int) {
    if k == m {
        result.append(arr.map { String($0) }.joined(separator: " ") + "\n")
        return
    }
    
    for i in 1...n {
        arr[k] = i
        solve(k + 1)
    }
}

solve(0)
print(result)
```
# 15652. N과M(4)
```swift
let nm = readLine()!.split(separator: " ").map { Int($0)! }
let (n, m) = (nm[0], nm[1])
var arr = Array(repeating: 0, count: m)
var vis = Array(repeating: false, count: n+1)
var result = ""

func solve(_ k:Int, _ cur:Int) {
    var cur = cur
    if k == m {
        for _ in 0..<m {
            result.append(arr.map { String($0) }.joined(separator: " ") + "\n")
            return
        }
    }
    if k != 0 {cur = arr[k-1]}
    for i in cur...n {
            arr[k] = i
            solve(k+1, cur)
    }
    
}

solve(0, 1)
print(result)
```
# 15654. N과M(5)
```swift
let nm = readLine()!.split(separator: " ").map{Int($0)!} // 3 1
let (n,m) = (nm[0], nm[1])
var arr = Array(repeating: 0 , count : m) // 1
var vis = Array(repeating: false, count: 10001)

var result = ""

var nums = readLine()!.split(separator: " ").map{Int($0)!}

func solve(_ k:Int) {
    if k == m{
        result.append(arr.map{ String($0) }.joined(separator: " ") + "\n")
        return
    }
    
    for i in nums.sorted() {
        if !vis[i] {
            arr[k] = i
            vis[i] = true
            solve(k+1)
            vis[i] = false
        }
    }
}

solve(0)
print(result)
```
# 15655. N과M(6)
```swift
let nm = readLine()!.split(separator: " ").map{Int($0)!}
let (n,m) = (nm[0], nm[1])

var nums = readLine()!.split(separator: " ").map{Int($0)!}
nums = nums.sorted()
var vis = Array(repeating: false, count: 10001)
var arr = Array(repeating: 0, count: m)
var result = ""

func solve(_ k:Int, _ current:Int) {
    var cur = current
    
    if k == m {
        result.append(arr.map { String($0) }.joined(separator: " ") + "\n")
        return
    }
    
    for i in cur..<n {
        arr[k] = nums[i]
        cur += 1
        solve(k+1, cur)
    }
            
}


solve(0, 0)
print(result)
```
