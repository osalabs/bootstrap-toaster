# Bootstrap Toaster

A lightweight and customizable toast notification library built on top of Bootstrap 5

## Features

- Automatically stack multiple toasts and hides them after a timeout
- Supports HTML content.
- Customizable themes.
- Provides helper methods for common toast types (success, warning, danger, info, primary).
- Includes a "Close All" feature to close multiple visible toasts at once
- Emits custom events for toast actions.

![image](https://github.com/osalabs/bootstrap-toaster/assets/1141095/1e9d4aa7-6ec8-438e-b539-3d8d9248ea23)

![image](https://github.com/osalabs/bootstrap-toaster/assets/1141095/4ad85c95-5d01-4637-9cfc-16d2a44b742e)

## Installation

1. Include the Bootstrap 5 CSS and JS files in your HTML:

```html
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet">
    <script src="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/js/bootstrap.bundle.min.js"></script>
```

2. Include the Toaster script after Bootstrap:

```html
<script src="path/to/bootstrap-toaster.js"></script>
```

## Usage

### Showing a Simple Toast

```javascript
Toast('Hello World');
```

### Shortcuts for Standard Toasts

```javascript
ToastSuccess('This is a Success!');
ToastWarning('This is a Warning!');
ToastDanger('This is a Danger!');
ToastInfo('This is an Info!');
ToastPrimary('This is a Primary!');
```

### Custom Toast with Options

info color with allowed html and hide delayed up to 7s

```javascript
Toast('Custom <b>Bold</b> Message', { theme: 'text-bg-info', html: true, delay: 7000 });
```

### Custom Events

Toast events can be listened to on the document body for actions like toast.shown, toast.hidden, and toast.hidden.all.

```javascript
document.body.addEventListener('toast.shown', function(event) {
    console.log('Toast shown:', event.detail.message);
});

document.body.addEventListener('toast.hidden', function(event) {
    console.log('Toast hidden:', event.detail.message);
});

document.body.addEventListener('toast.hidden.all', function(event) {
    console.log('All toasts hidden');
});
```

## API

### `Toast(message, options)`

-   `message` (string): The content of the toast.
-   `options` (object): Optional settings for the toast.

#### Options

-   `theme` (string): The Bootstrap theme class for the toast (e.g., `text-bg-success`, `text-bg-danger`).
-   `animation` (boolean): Whether to animate the toast (default: `true`).
-   `autohide` (boolean): Whether the toast should automatically hide (default: `true`).
-   `delay` (number): Delay in milliseconds before the toast hides (default: `5000`).
-   `html` (boolean): Whether the message is HTML content (default: `false`).
