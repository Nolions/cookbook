# 開放封閉原則(OCP)

對於擴展是開放的，但對於修改是封閉的

```php
interface Payment
{
    public function pay($receipt);
}

class creditCard implements Payment
{
    public function pay($receipt)
    {
        // ...
    }
}


class cash implements Payment
{
    public function pay($receipt)
    {
        // ...
    }
}


class Payment
{
    public function pay(Receipt $receipt, Payment $payment)
    {
        $payment->pay($receipt);
    }
}
```