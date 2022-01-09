# First bad version
## https://leetcode.com/problems/first-bad-version

# Implementation 1 : Naive(Brute Force) Time Limit Exceeded
```java
/* The isBadVersion API is defined in the parent class VersionControl.
      boolean isBadVersion(int version); */

public class Solution extends VersionControl {
    public int firstBadVersion(int n) {
        for(int i = 1; i <= n; i++) {
            if(isBadVersion(i))
                return i;
        }
        return -1;
    }
}
```
