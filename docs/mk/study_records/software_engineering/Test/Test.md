# Testing

## Unit tests

> A unit test validates the operation of a small, self-contained piece of code, such as a single
method or function in Python.

## Positive *and* negative tests

* **Positive tests**: code should give correct answer with various inputs

* **Negative tests**: code should crash as expected given invalid inputs, rather than lying

Bad input should be expected and should fail early and explicitly.

Testing should ensure that explicit failures do indeed happen.

## Mock tests

> A test that replaces an external dependency of the object being tested with a simplified / custom implementation or return value of said object.

在测试搜索设备功能时，我会 mock `ping` 的返回结果，而不是去真实 ping 一个设备 IP，这样测试会更快、更稳定，也不会依赖网络环境。

## Integration (or system) tests

> An integration test validates how multiple units interact with each other, often
mimicking a common analysis pipeline or workflow that users of the software might employ.