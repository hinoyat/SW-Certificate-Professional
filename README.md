# SW-Certificate-Professional

# 나만의 룰
> * 한 문제를 풀더라도 다른 사람들의 풀이를 보며 시간복잡도, 메모리 따지기
> * 최적화를 위한 필수 배경지식, 기법 정리
> * 시간을 정해놓고 주어진 시간을 분배하기 (분석 - 구현 - 최적화)
> * 라이브러리 사용이 가능해도 직접 구현부터 시도


## 폴더 구조

```
src/main/java/algorithm/
├── datastructure/
│   ├── array/
│   │   └── ArrayImpl.java
│   ├── linkedlist/
│   │   └── LinkedListImpl.java 
│   ├── stack/
│   │   └── StackImpl.java
│   ├── queue/
│   │   └── QueueImpl.java
│   └── tree/
│       └── TreeImpl.java
├── basic/
│   ├── sort/
│   │   ├── BubbleSort.java
│   │   ├── QuickSort.java
│   │   └── MergeSort.java
│   ├── search/
│   │   ├── BinarySearch.java
│   │   └── SequentialSearch.java
│   └── recursive/
│       └── RecursiveImpl.java
└── advanced/
    ├── dp/
    │   └── DynamicProgramming.java
    ├── greedy/
    │   └── GreedyAlgorithm.java 
    └── graph/
        ├── DFS.java
        └── BFS.java

src/main/java/problem/
├── mysolution/
├── othersolution/
└── optimization/

src/main/java/review/
├── mistake/
│   ├── timeout/
│   ├── memory/
│   └── runtime/
└── solution/

test/
└── java/
    ├── datastructure/
    ├── algorithm/
    └── problem/

resources/
├── input/
└── output/
```

각 .java 파일의 패키지 선언:
```java
// 자료구조 구현
package algorithm.datastructure.array;
package algorithm.datastructure.linkedlist;

// 알고리즘 구현
package algorithm.basic.sort;
package algorithm.advanced.dp;

// 문제풀이 
package problem.mysolution;
package problem.othersolution;

// 실수노트
package review.mistake.timeout;
package review.solution;
```


# 성능 테스트
자바에서 시간과 메모리 측정을 위한 유틸리티 클래스입니다.

## TimeCheck
```java
public class TimeCheck {
    public static void measureTime(Runnable task) {
        long startTime = System.nanoTime();
        task.run();
        long endTime = System.nanoTime();
        System.out.println("실행시간: " + (endTime - startTime) / 1000000.0 + "ms");
    }
}
```

## MemoryCheck
```java
public class MemoryCheck {
    public static void measureMemory() {
        Runtime runtime = Runtime.getRuntime();
        long usedMemory = runtime.totalMemory() - runtime.freeMemory();
        System.out.println("사용 메모리: " + usedMemory / 1024 / 1024 + "MB");
    }
}
```

## 사용 예시
```java
public class PerformanceTest {
    public static void main(String[] args) {
        // 시간 측정
        TimeCheck.measureTime(() -> {
            // 테스트할 코드
        });

        // 메모리 측정
        MemoryCheck.measureMemory();
        
        // 테스트 전후 비교
        MemoryCheck.measureMemory();
        // 코드 실행
        MemoryCheck.measureMemory();
    }
}
```