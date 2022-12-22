介面隔離原則(ISP)

龐大臃腫的介面拆分成更小且更具體的介面，讓客戶端只需要實作它們真正需要的方法或功能，更有效降低耦合

```php
interface CloudHostingProvider
{
    public function createServer(string $region);
    public function listServer(string $region);
}

interface CdnProvider
{
    public function getCdnAddress();
}

interface CloudStorageProvider
{
    public function storeFile(string $name);
    public function getFile(string $name);
}

class AWS implements CloudHostingProvider, CdnProvider, CloudStorageProvider
{
    // ...
}

class GCP implements CloudStorageProvider
{
    public function storeFile(string $name)
    {
        // ...
    }

    public function getFile(string $name)
    {
        // ...
    }
}

```
