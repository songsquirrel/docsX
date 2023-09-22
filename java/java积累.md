1. 函数式编程



2. future 与 CompletableFuture  
   创建线程可通过继承Thread或者实现Runnable接口，但是这两种方法均无返回值。java1.5之后的Callable和Future接口解决了这个问题。

    `Future` 获得异步执行结果，要么调用阻塞方法`get()`，要么轮询`isDone()`是否为`true`，均会导致主线程被迫等待。

    Java8开始引入`CompletableFuture`, 可以传入回调对象, 当异步任务完成或者发生异常时, 自动调用回调对象的回调方法.

    ```java
    import java.util.concurrent.CompletableFuture;

    public class Main {
    public static void main(String[] args) throws Exception {
        // 创建异步执行任务:
        CompletableFuture<Double> cf = CompletableFuture.supplyAsync(Main::fetchPrice);
        // 如果执行成功:
        cf.thenAccept((result) -> {
            System.out.println("price: " + result);
        });
        // 如果执行异常:
        cf.exceptionally((e) -> {
            e.printStackTrace();
            return null;
        });
        // 主线程不要立刻结束，否则CompletableFuture默认使用的线程池会立刻关闭:
        Thread.sleep(200);
    }

    static Double fetchPrice() {
        try {
            Thread.sleep(100);
        } catch (InterruptedException e) {
        }
        if (Math.random() < 0.3) {
            throw new RuntimeException("fetch price failed!");
        }
        return 5 + Math.random() * 20;
    }
}
    ```

    多个`CompletableFuture`可以串行或并行执行, 可实现多任务异步编排.

   多任务异步编排框架：Gobrs-Async



