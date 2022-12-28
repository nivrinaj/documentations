<!-- Global site tag (gtag.js) - Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=G-EXAMPLE"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', 'G-EXAMPLE');
{% if first_time_accessed %}
gtag("event", "purchase", {
    transaction_id: "{{ order.order_number }}",
    value: {{ total_price | times: 0.01 }},
    tax: {{ tax_price | times: 0.01 }},
    shipping: {{ shipping_price | times: 0.01 }},
    currency: "{{ order.currency }}",
    items: [
     {% for line_item in line_items %}
     {
      item_id: "{{ line_item.product_id }}",
      item_name: "{{ line_item.title | remove: "'" | remove: '"' }}",
      currency: "{{ order.currency }}",
      price: {{ line_item.original_price | times: 0.01 }},
      quantity: {{ line_item.quantity }}
    },
    {% endfor %}
    ]
});
{% endif %}
</script>
