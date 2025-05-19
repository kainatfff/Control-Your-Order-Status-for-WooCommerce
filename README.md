// Automatically mark virtual orders as completed
add_action('woocommerce_order_status_processing', 'auto_complete_virtual_orders');
function auto_complete_virtual_orders($order_id) {
    $order = wc_get_order($order_id);
    if ($order->is_virtual()) {
        $order->update_status('completed');
    }
}
