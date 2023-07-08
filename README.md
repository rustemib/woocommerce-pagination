# woocommerce
Изменение количества элементов в поле пагинации
втавить в function.php темы


function custom_woocommerce_pagination_args($args) {
    $args['end_size'] = 1; // Количество элементов в начале и конце пагинации
    $args['mid_size'] = 0; // Количество элементов в середине пагинации
    $args['prev_next'] = true; // Отображение кнопок "Предыдущая" и "Следующая"
    $args['prev_text'] = '&laquo;'; // Текст кнопки "Предыдущая"
    $args['next_text'] = '&raquo;'; // Текст кнопки "Следующая"
    $args['type'] = 'list'; // Вид пагинации (list - список, numbers - числа, prev_next - кнопки "Предыдущая" и "Следующая")

    // Установите желаемое количество элементов на страницу
    $args['per_page'] = 12;

    return $args;
}
add_filter('woocommerce_pagination_args', 'custom_woocommerce_pagination_args', 10, 1);
