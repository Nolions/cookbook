# 單一職責原則(SRP)

一個 class/method 只做一件事，一個模組應有且只有一個理由會使其改變

```php
class Book {
    function getTitle() {
        return "A Great Book";
    }

    function getAuthor() {
        return "John Doe";
    }

    function turnPage() {
        // pointer to next page
    }

    function getCurrentPage() {
        return "current page content";
    }
}

class SimpleFilePersistence {
    function save(Book $book) {
        $filename = '/documents/' . $book->getTitle() . ' - ' . $book->getAuthor();
        file_put_contents($filename, serialize($book));
    }
}
```