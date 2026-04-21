<?php
// Shopping Cart Items
$cartItems = [
    [
        'id' => 1,
        'name' => 'Laptop',
        'price' => 999.99,
        'quantity' => 1
    ],
    [
        'id' => 2,
        'name' => 'Mouse',
        'price' => 29.99,
        'quantity' => 2
    ],
    [
        'id' => 3,
        'name' => 'Keyboard',
        'price' => 79.99,
        'quantity' => 1
    ]
];

// Calculate total price
$totalPrice = 0;

// Display cart items using foreach loop
echo "<h2>Shopping Cart</h2>";
echo "<table border='1' cellpadding='10'>";
echo "<tr><th>Product</th><th>Price</th><th>Quantity</th><th>Subtotal</th></tr>";

foreach ($cartItems as $item) {
    $subtotal = $item['price'] * $item['quantity'];
    $totalPrice += $subtotal;
    
    echo "<tr>";
    echo "<td>" . htmlspecialchars($item['name']) . "</td>";
    echo "<td>$" . number_format($item['price'], 2) . "</td>";
    echo "<td>" . $item['quantity'] . "</td>";
    echo "<td>$" . number_format($subtotal, 2) . "</td>";
    echo "</tr>";
}

echo "</table>";
echo "<h3>Total: $" . number_format($totalPrice, 2) . "</h3>";

// Display item count
$totalItems = 0;
foreach ($cartItems as $item) {
    $totalItems += $item['quantity'];
}
echo "<p>Total Items in Cart: " . $totalItems . "</p>";
?>
