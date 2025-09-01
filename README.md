import React from "react";

// Sample Product Data
const products = [
  {
    id: 1,
    name: "Wireless Headphones",
    price: "$59.99",
    image:
      "https://images.unsplash.com/photo-1585386959984-a4155228c3d4?w=400",
  },
  {
    id: 2,
    name: "Smart Watch",
    price: "$129.99",
    image:
      "https://images.unsplash.com/photo-1522312346375-d1a52e2b99b3?w=400",
  },
  {
    id: 3,
    name: "Gaming Mouse",
    price: "$39.99",
    image:
      "https://images.unsplash.com/photo-1610484826967-09c86fc06862?w=400",
  },
];

// Product Card Component
function ProductCard({ product }) {
  return (
    <div className="bg-white shadow-lg rounded-2xl p-4 w-64 hover:scale-105 transition-transform">
      <img
        src={product.image}
        alt={product.name}
        className="rounded-lg w-full h-40 object-cover"
      />
      <h2 className="text-lg font-semibold mt-3">{product.name}</h2>
      <p className="text-gray-600">{product.price}</p>
      <button className="mt-3 w-full bg-blue-500 text-white py-2 rounded-lg hover:bg-blue-600">
        Add to Cart
      </button>
    </div>
  );
}

// Main App Component
export default function App() {
  return (
    <div className="min-h-screen bg-gray-100 flex flex-col items-center p-6">
      <h1 className="text-2xl font-bold mb-6">Product List</h1>
      <div className="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 gap-6">
        {products.map((p) => (
          <ProductCard key={p.id} product={p} />
        ))}
      </div>
    </div>
  );
}
