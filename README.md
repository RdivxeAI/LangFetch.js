
![LangFetch Cover](https://raw.githubusercontent.com/RdivxeAI/LangFetch.js/refs/heads/main/LangFetch.png)

# LangFetch.js

A developer-friendly JavaScript library for sending HTTP requests using natural language prompts in **Arabic** or **English**. Supports **GET**, **POST**, **JSON**, **FormData**, **file uploads**, dynamic parameters, automatic type conversion, and repeated requests.

Load the library directly from CDN:

```html
<script src="https://cdn.jsdelivr.net/gh/RdivxeAI/LangFetch.js/LangFetch.js"></script>
````

---

## Features

* Send HTTP requests using **natural language prompts**.
* Automatic placeholder definition for variables.
* Supports **GET** and **POST** requests.
* JSON, FormData, and file uploads supported.
* Dynamic parameters and automatic type conversion.
* Repeat requests easily with `proRepeat`.
* Fully compatible with Arabic and English prompts.
* Handles errors gracefully and logs them to the console.

---

## Installation

**1. Via CDN (recommended for web projects):**

```html
<script src="https://cdn.jsdelivr.net/gh/RdivxeAI/LangFetch.js/LangFetch.js"></script>
```

**2. Via npm (for Node.js projects):**

```bash
npm install langfetch
```

---

## Usage

### English Example

```html
<prompt style="display:none;">
Send a POST request to https://example.com/api with params: {"name":"John"} and store the response in variable result of type object
</prompt>

<script>
  // Run a single prompt
  pro("Send a GET request to https://example.com/status and store the response in statusVar");

  // Repeat a request 5 times
  proRepeat("Send a POST request to https://example.com/log with params: {\"event\":\"click\"}", 5);

  // Run all <prompt> tags automatically
  LangFetch.runAllPrompts();
</script>
```

### Arabic Example

```html
<prompt style="display:none;">
ابعت POST الى https://example.com/api مع params: {"name":"عمرو"} وخزن النتيجة في المتغير result من النوع object
</prompt>

<script>
  // شغّل كل الـ prompts الموجودة في الصفحة
  LangFetch.runAllPrompts();

  // مثال على تكرار طلب 3 مرات
  proRepeat("ابعت GET الى https://example.com/status وخزنها في المتغير statusVar", 3);
</script>
```

---

## Extended Examples

```html
<prompt style="display:none;">
ابعت لـ https://example.com/api?query=system_test وحط النتيجة في المتغير result1 من النوع object
</prompt>

<prompt style="display:none;">
هات من https://example.com/api?query=example_name وحط النتيجة في المتغير result2 من النوع string
</prompt>

<script src="LangFetch.js"></script>

<script>
  // أمثلة استخدام:

  // رفع ملف من متغير
  const myFile = new File(["Hello world"], "hello.txt", {type:"text/plain"});
  window.myFile = myFile;

  pro('ارفع myFile إلى https://example.com/api وحط النتيجة في المتغير uploadResult من النوع object')
    .then(res => console.log("uploadResult:", res));

  // GET / POST طبيعي
  pro('ابعت لـ https://example.com/api?query=system_test وحط النتيجة في المتغير result1 من النوع object')
    .then(res => console.log("result1:", res));

  pro('هات من https://example.com/api?query=example_name وحط النتيجة في المتغير result2 من النوع string')
    .then(res => console.log("result2:", res));

  // استخدام التكرار
  proRepeat('هات من https://example.com/api?query=example_name وحط النتيجة في المتغير repeatedResult من النوع string', 5)
    .then(results => console.log("النتايج المتكررة:", results));
</script>
```

---

## API Reference

| Function                                     | Description                              |
| -------------------------------------------- | ---------------------------------------- |
| `pro(promptText)`                            | Run a single natural language prompt.    |
| `proRepeat(promptText, times)`               | Run a prompt multiple times.             |
| `LangFetch.runAllPrompts()`                  | Execute all `<prompt>` tags on the page. |
| `LangFetch.definePlaceholder(varName, type)` | Manually define a placeholder variable.  |
| `LangFetch.values`                           | Access all defined placeholder values.   |

---

## Notes

* Variables defined in prompts are automatically created on the `window` object.
* If a placeholder variable already exists, it will not be overwritten unless explicitly set.
* Supports **JSON**, **FormData**, and file uploads with dynamic placeholders.
* Automatic type conversion based on placeholder type (`string`, `number`, `boolean`, `object`, `array`).
* Error handling logs issues in the console but prevents the application from breaking.

---

## Example Use Cases

* Quickly test APIs with natural language prompts.
* Collect form data dynamically and send it to backend endpoints.
* Automate repetitive requests with minimal code.
* Integrate Arabic or English prompts directly into your front-end code.

---

## Contributing

Contributions, issues, and feature requests are welcome!
Feel free to fork the repo and submit pull requests.

---

## License

MIT License – Free to use, modify, and distribute.

---

> Written by **Amr Twig**, Rdivxe LLC – designed for professional developers.

```

