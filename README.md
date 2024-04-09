<h1>README PROYECTO FINAL GRUPO 2<h2>

<p>
Vamos a hacer un e-commerce de venta de zapatillas. Apuntamos a todos las personas adultas que quieran comprar zapatillas casuales y deportivas. Entre nuestros productos se van a encontrar:
</p>
<ul>
  <li>Zapatillas Casuales</li>
  <li>Zapatillas Deportivas</li>
</ul>

<p>
Las paginas en las que nos inspiramos y tomamos algunas ideas fueron, entre otras:
</p>
<ul>
  <li>Adidas</li>
  <li>HyM</li>
  <li>Dash</li>
  <li>Puma</li>
  <li>Amazon</li>
</ul>

Script para poblar base de datos inicial:

---

CREATE TABLE `users` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`name` varchar(50) NOT NULL,
`surname` varchar(50) NOT NULL,
`email` varchar(100) NOT NULL,
`password` varchar(150) NOT NULL,
`image` blob DEFAULT NULL,
`id_user_category` int(11) NOT NULL,
PRIMARY KEY (`id`)
);

CREATE TABLE `user_categories` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`category_name` varchar(50) NOT NULL,
PRIMARY KEY (`id`)
);

CREATE TABLE `facturas` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`price` bigint(20) NOT NULL,
`id_user` int(11) NOT NULL,
PRIMARY KEY (`id`)
);

CREATE TABLE `factura_product` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`id_factura` int(11) NOT NULL,
`id_product` int(11) NOT NULL,
`quantity` int(11) NOT NULL,
PRIMARY KEY (`id`)
);

CREATE TABLE `products` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`name` varchar(100) NOT NULL,
`description` text NOT NULL,
`image` blob DEFAULT NULL,
`price` bigint(20) NOT NULL,
`id_product_category` int(11) NOT NULL,
`banner` blob DEFAULT NULL,
PRIMARY KEY (`id`)
);

CREATE TABLE `product_categories` (
`id` int(11) NOT NULL AUTO_INCREMENT,
`category_name` varchar(50) NOT NULL,
PRIMARY KEY (`id`)
);

CREATE TABLE productos_destacados (
id INT NOT NULL AUTO_INCREMENT,
product_id INT NOT NULL,
PRIMARY KEY (id)
);

ALTER TABLE users ADD FOREIGN KEY(id_user_category) REFERENCES user_categories(id);

ALTER TABLE facturas ADD FOREIGN KEY(id_user) REFERENCES users(id);

ALTER TABLE factura_product ADD FOREIGN KEY(id_factura) REFERENCES facturas(id);
ALTER TABLE factura_product ADD FOREIGN KEY(id_product) REFERENCES products(id);

ALTER TABLE products ADD FOREIGN KEY(id_product_category) REFERENCES product_categories(id);

INSERT INTO `user_categories` (`id`, `category_name`)
VALUES (1, 'usuario_comun'), (2, 'admin');

INSERT INTO `productos_destacados` (`id`, `product_id`)
VALUES (1, 0), (2, 0);

INSERT INTO `product_categories` (`id`, `category_name`)
VALUES (1, 'Deportiva'), (2, 'Casual');

---

<h3>Enlace al Trello:</h3>
<p>https://trello.com/b/piRRu6U8/proyecto-integrador</p>
#   p r o y e c t o F i n a l G r u p o 2 
 
 
