<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Black Yak Himalayan - Casaca Premium</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Arial', sans-serif;
            background: #0a0a0a;
            color: #fff;
            overflow-x: hidden;
        }

        .header {
            position: fixed;
            top: 0;
            width: 100%;
            padding: 25px 50px;
            background: rgba(10, 10, 10, 0.95);
            backdrop-filter: blur(10px);
            z-index: 1000;
            border-bottom: 1px solid rgba(255, 140, 0, 0.2);
        }

        .logo {
            font-size: 24px;
            font-weight: bold;
            letter-spacing: 2px;
            background: linear-gradient(135deg, #ff8c00, #ffa500);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
        }

        .hero-section {
            min-height: 100vh;
            padding: 120px 50px 50px;
            display: flex;
            align-items: center;
            justify-content: center;
        }

        .main-container {
            max-width: 1600px;
            width: 100%;
            margin: 0 auto;
        }

        .product-showcase {
            display: grid;
            grid-template-columns: 1.2fr 0.8fr;
            gap: 80px;
            align-items: start;
        }

        .gallery-section {
            position: sticky;
            top: 120px;
        }

        .main-image-container {
            width: 100%;
            height: 750px;
            border-radius: 30px;
            overflow: hidden;
            margin-bottom: 30px;
            background: linear-gradient(135deg, rgba(255, 140, 0, 0.1), rgba(0, 0, 0, 0.5));
            box-shadow: 0 40px 100px rgba(255, 140, 0, 0.3);
            position: relative;
        }

        .main-image {
            width: 100%;
            height: 100%;
            object-fit: cover;
            transition: transform 0.6s ease;
        }

        .main-image-container:hover .main-image {
            transform: scale(1.05);
        }

        .thumbnails {
            display: grid;
            grid-template-columns: repeat(3, 1fr);
            gap: 20px;
        }

        .thumbnail-wrapper {
            height: 200px;
            border-radius: 20px;
            overflow: hidden;
            cursor: pointer;
            position: relative;
            border: 3px solid transparent;
            transition: all 0.4s ease;
        }

        .thumbnail-wrapper::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            right: 0;
            bottom: 0;
            background: rgba(0, 0, 0, 0.4);
            transition: all 0.4s ease;
            z-index: 1;
        }

        .thumbnail-wrapper:hover::before,
        .thumbnail-wrapper.active::before {
            background: rgba(255, 140, 0, 0.2);
        }

        .thumbnail-wrapper.active {
            border-color: #ff8c00;
            transform: scale(1.05);
        }

        .thumbnail {
            width: 100%;
            height: 100%;
            object-fit: cover;
        }

        .info-section {
            padding: 40px 0;
        }

        .badge {
            display: inline-block;
            padding: 8px 20px;
            background: rgba(255, 140, 0, 0.2);
            border: 1px solid #ff8c00;
            border-radius: 30px;
            font-size: 12px;
            letter-spacing: 2px;
            text-transform: uppercase;
            margin-bottom: 20px;
            animation: fadeInUp 0.8s ease;
        }

        @keyframes fadeInUp {
            from {
                opacity: 0;
                transform: translateY(30px);
            }
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }

        h1 {
            font-size: 64px;
            line-height: 1.2;
            margin-bottom: 20px;
            font-weight: 300;
            letter-spacing: -2px;
            animation: fadeInUp 0.8s ease 0.2s backwards;
        }

        .highlight {
            color: #ff8c00;
            font-weight: 600;
        }

        .subtitle {
            font-size: 20px;
            color: #999;
            margin-bottom: 40px;
            line-height: 1.6;
            animation: fadeInUp 0.8s ease 0.4s backwards;
        }

        .price-section {
            display: flex;
            align-items: baseline;
            gap: 15px;
            margin-bottom: 50px;
            animation: fadeInUp 0.8s ease 0.6s backwards;
        }

        .price {
            font-size: 72px;
            font-weight: 700;
            color: #ff8c00;
            letter-spacing: -3px;
        }

        .currency {
            font-size: 28px;
            color: #666;
        }

        .condition-badge {
            background: linear-gradient(135deg, #ff8c00, #ffa500);
            padding: 12px 25px;
            border-radius: 30px;
            font-size: 16px;
            font-weight: 600;
            display: inline-flex;
            align-items: center;
            gap: 8px;
        }

        .specs-grid {
            display: grid;
            grid-template-columns: repeat(2, 1fr);
            gap: 25px;
            margin-bottom: 50px;
            animation: fadeInUp 0.8s ease 0.8s backwards;
        }

        .spec-item {
            padding: 30px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            border: 1px solid rgba(255, 140, 0, 0.2);
            transition: all 0.4s ease;
        }

        .spec-item:hover {
            background: rgba(255, 140, 0, 0.1);
            border-color: #ff8c00;
            transform: translateY(-5px);
        }

        .spec-icon {
            font-size: 32px;
            margin-bottom: 15px;
            display: block;
        }

        .spec-label {
            font-size: 12px;
            color: #666;
            text-transform: uppercase;
            letter-spacing: 1px;
            margin-bottom: 8px;
        }

        .spec-value {
            font-size: 18px;
            color: #fff;
            font-weight: 500;
        }

        .description {
            font-size: 18px;
            line-height: 1.8;
            color: #aaa;
            margin-bottom: 50px;
            animation: fadeInUp 0.8s ease 1s backwards;
        }

        .cta-buttons {
            display: flex;
            gap: 20px;
            margin-bottom: 40px;
            animation: fadeInUp 0.8s ease 1.2s backwards;
        }

        .btn {
            flex: 1;
            padding: 22px 40px;
            font-size: 18px;
            font-weight: 600;
            border: none;
            border-radius: 50px;
            cursor: pointer;
            transition: all 0.4s ease;
            text-decoration: none;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 12px;
        }

        .btn-primary {
            background: linear-gradient(135deg, #ff8c00, #ffa500);
            color: #fff;
            box-shadow: 0 20px 40px rgba(255, 140, 0, 0.4);
        }

        .btn-primary:hover {
            box-shadow: 0 25px 50px rgba(255, 140, 0, 0.6);
            transform: translateY(-3px);
        }

        .contact-info {
            padding: 30px;
            background: rgba(255, 255, 255, 0.03);
            border-radius: 20px;
            border: 1px solid rgba(255, 140, 0, 0.2);
            animation: fadeInUp 0.8s ease 1.4s backwards;
        }

        .contact-item {
            display: flex;
            align-items: center;
            gap: 15px;
            margin-bottom: 15px;
            font-size: 16px;
            color: #aaa;
        }

        .contact-item:last-child {
            margin-bottom: 0;
        }

        .contact-icon {
            width: 24px;
            height: 24px;
            fill: #ff8c00;
        }

        @media (max-width: 1200px) {
            .product-showcase {
                grid-template-columns: 1fr;
                gap: 50px;
            }

            .gallery-section {
                position: relative;
                top: 0;
            }

            .main-image-container {
                height: 600px;
            }

            h1 {
                font-size: 48px;
            }

            .price {
                font-size: 56px;
            }
        }

        @media (max-width: 768px) {
            .header {
                padding: 20px 30px;
            }

            .hero-section {
                padding: 100px 30px 30px;
            }

            .thumbnails {
                grid-template-columns: repeat(3, 1fr);
                gap: 10px;
            }

            .thumbnail-wrapper {
                height: 120px;
            }

            h1 {
                font-size: 36px;
            }

            .price {
                font-size: 48px;
            }

            .specs-grid {
                grid-template-columns: 1fr;
            }

            .cta-buttons {
                flex-direction: column;
            }
        }
    </style>
</head>
<body>
    <header class="header">
        <div class="logo">BLACK YAK</div>
    </header>

    <section class="hero-section">
        <div class="main-container">
            <div class="product-showcase">
                <div class="gallery-section">
                    <div class="main-image-container">
                        <img id="mainImage" class="main-image" src="anteriror.png" alt="Casaca Black Yak Himalayan">
                    </div>
                    <div class="thumbnails">
                        <div class="thumbnail-wrapper active" onclick="changeImage(0)">
                            <img class="thumbnail" src="anteriror.png" alt="Vista frontal">
                        </div>
                        <div class="thumbnail-wrapper" onclick="changeImage(1)">
                            <img class="thumbnail" src="marca.png" alt="Vista detalle">
                        </div>
                        <div class="thumbnail-wrapper" onclick="changeImage(2)">
                            <img class="thumbnail" src="posterior.png" alt="Vista posterior">
                        </div>
                    </div>
                </div>

                <div class="info-section">
                    <span class="badge">TALLA - L   105</span>
                    
                    <h1>Black Yak <span class="highlight">Himalayan</span></h1>
                    
                    <p class="subtitle">
                        Casaca de expedición premium con relleno de pluma. Diseñada para conquistar las montañas más exigentes del mundo.
                    </p>

                    <div class="price-section">
                        <span class="price">S/ 250</span>
                        <span class="condition-badge">⭐ Estado 9/10</span>
                    </div>

                    <div class="specs-grid">
                        <div class="spec-item">
                            <span class="spec-icon">🪶</span>
                            <div class="spec-label">Material</div>
                            <div class="spec-value">Pluma Premium</div>
                        </div>
                        <div class="spec-item">
                            <span class="spec-icon">🎨</span>
                            <div class="spec-label">Colores</div>
                            <div class="spec-value">Naranja / Negro</div>
                        </div>
                        <div class="spec-item">
                            <span class="spec-icon">🏔️</span>
                            <div class="spec-label">Uso</div>
                            <div class="spec-value">Expedición Extrema</div>
                        </div>
                        <div class="spec-item">
                            <span class="spec-icon">🌡️</span>
                            <div class="spec-label">Temperatura</div>
                            <div class="spec-value">-20°C ~ 5°C</div>
                        </div>
                    </div>

                    <p class="description">
                        Esta casaca Black Yak Himalayan representa la cúspide de la tecnología en ropa de montaña. Con relleno de pluma de alta densidad, proporciona un aislamiento térmico excepcional sin comprometer la movilidad. El diseño icónico en naranja y negro no solo es visualmente impactante, sino que también mejora la visibilidad en condiciones extremas. Perfecta para alpinismo, trekking en alta montaña y cualquier aventura que demande el máximo rendimiento.
                    </p>

                    <div class="cta-buttons">
                        <a href="https://wa.me/51900204360?text=Hola!%20Estoy%20interesado%20en%20la%20casaca%20Black%20Yak%20Himalayan%20de%20S/%20160" class="btn btn-primary" target="_blank">
                            <svg width="24" height="24" viewBox="0 0 24 24" fill="currentColor">
                                <path d="M17.472 14.382c-.297-.149-1.758-.867-2.03-.967-.273-.099-.471-.148-.67.15-.197.297-.767.966-.94 1.164-.173.199-.347.223-.644.075-.297-.15-1.255-.463-2.39-1.475-.883-.788-1.48-1.761-1.653-2.059-.173-.297-.018-.458.13-.606.134-.133.298-.347.446-.52.149-.174.198-.298.298-.497.099-.198.05-.371-.025-.52-.075-.149-.669-1.612-.916-2.207-.242-.579-.487-.5-.669-.51-.173-.008-.371-.01-.57-.01-.198 0-.52.074-.792.372-.272.297-1.04 1.016-1.04 2.479 0 1.462 1.065 2.875 1.213 3.074.149.198 2.096 3.2 5.077 4.487.709.306 1.262.489 1.694.625.712.227 1.36.195 1.871.118.571-.085 1.758-.719 2.006-1.413.248-.694.248-1.289.173-1.413-.074-.124-.272-.198-.57-.347m-5.421 7.403h-.004a9.87 9.87 0 01-5.031-1.378l-.361-.214-3.741.982.998-3.648-.235-.374a9.86 9.86 0 01-1.51-5.26c.001-5.45 4.436-9.884 9.888-9.884 2.64 0 5.122 1.03 6.988 2.898a9.825 9.825 0 012.893 6.994c-.003 5.45-4.437 9.884-9.885 9.884m8.413-18.297A11.815 11.815 0 0012.05 0C5.495 0 .16 5.335.157 11.892c0 2.096.547 4.142 1.588 5.945L.057 24l6.305-1.654a11.882 11.882 0 005.683 1.448h.005c6.554 0 11.89-5.335 11.893-11.893a11.821 11.821 0 00-3.48-8.413z"/>
                            </svg>
                            Comprar por WhatsApp
                        </a>
                    </div>

                    <div class="contact-info">
                        <div class="contact-item">
                            <svg class="contact-icon" viewBox="0 0 24 24">
                                <path d="M12 2C8.13 2 5 5.13 5 9c0 5.25 7 13 7 13s7-7.75 7-13c0-3.87-3.13-7-7-7zm0 9.5c-1.38 0-2.5-1.12-2.5-2.5s1.12-2.5 2.5-2.5 2.5 1.12 2.5 2.5-1.12 2.5-2.5 2.5z"/>
                            </svg>
                            <span>Juliaca, Puno, Perú</span>
                        </div>
                        <div class="contact-item">
                            <svg class="contact-icon" viewBox="0 0 24 24">
                                <path d="M20 4H4c-1.1 0-1.99.9-1.99 2L2 18c0 1.1.9 2 2 2h16c1.1 0 2-.9 2-2V6c0-1.1-.9-2-2-2zm0 4l-8 5-8-5V6l8 5 8-5v2z"/>
                            </svg>
                            <span>Celular: 900 204 360</span>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <script>
        const images = [
            'anteriror.png',
            'marca.png',
            'posterior.png'
        ];

        function changeImage(index) {
            const mainImage = document.getElementById('mainImage');
            const thumbnails = document.querySelectorAll('.thumbnail-wrapper');
            
            mainImage.style.opacity = '0';
            setTimeout(() => {
                mainImage.src = images[index];
                mainImage.style.opacity = '1';
            }, 300);

            thumbnails.forEach((thumb, i) => {
                if (i === index) {
                    thumb.classList.add('active');
                } else {
                    thumb.classList.remove('active');
                }
            });
        }

        const mainImage = document.getElementById('mainImage');
        mainImage.style.transition = 'opacity 0.3s ease, transform 0.6s ease';
    </script>
</body>
</html>
