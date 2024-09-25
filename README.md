from fpdf import FPDF

# Crear una clase PDF personalizada
class PDF(FPDF):
    def header(self):
        self.set_font('Arial', 'B', 12)
        self.cell(0, 10, 'Presentación: Análisis Dimensional - Prueba Oral', 0, 1, 'C')

    def chapter_title(self, title):
        self.set_font('Arial', 'B', 14)
        self.cell(0, 10, title, 0, 1, 'L')
        self.ln(2)

    def chapter_body(self, body):
        self.set_font('Arial', '', 12)
        self.multi_cell(0, 10, body)
        self.ln()

    def add_figure_space(self, description):
        self.set_font('Arial', 'I', 12)
        self.cell(0, 10, f'[Espacio para gráfico: {description}]', 0, 1, 'C')
        self.ln()

# Crear el documento PDF
pdf = PDF()

# Agregar página
pdf.add_page()

# Diapositiva 1: Título
pdf.chapter_title('Diapositiva 1: Título e Imágenes')
pdf.chapter_body('Título: "Análisis Dimensional en Química: Aplicaciones Cotidianas"')
pdf.add_figure_space('Imágenes de vehículos, conversiones de unidades')

# Diapositiva 2: Introducción
pdf.chapter_title('Diapositiva 2: Introducción')
pdf.chapter_body(
    'El análisis dimensional es una herramienta fundamental en la química y otras ciencias. '
    'Permite convertir unidades y garantizar la consistencia de ecuaciones. Su uso es cotidiano '
    'en la vida diaria, como la medición de la velocidad o el cálculo del consumo de combustible '
    '(Brown et al., 2014).'
)

# Diapositiva 3: ¿Qué es el análisis dimensional?
pdf.chapter_title('Diapositiva 3: ¿Qué es el análisis dimensional?')
pdf.chapter_body(
    'El análisis dimensional es un método que permite convertir unidades de una magnitud física '
    'a otra, asegurando la coherencia entre las ecuaciones y los cálculos. '
    '(Brown et al., 2014).'
)

# Diapositiva 4: ¿Qué es un factor de conversión?
pdf.chapter_title('Diapositiva 4: ¿Qué es un factor de conversión?')
pdf.chapter_body(
    'Un factor de conversión es una relación entre dos unidades que permite convertir una '
    'unidad en otra equivalente. Ejemplo: 1 km = 1000 m. (Brown et al., 2014).'
)
pdf.chapter_body('Ejemplo: 5 km = 5000 m.')

# Diapositiva 5: Fórmula básica para el análisis dimensional
pdf.chapter_title('Diapositiva 5: Fórmula básica para el análisis dimensional')
pdf.chapter_body(
    'La fórmula base para el análisis dimensional es: '
    'Unidad dada × (Unidad deseada / Unidad dada) = Unidad deseada.'
)
pdf.chapter_body('Ejemplo: Convertir 5 horas a minutos: 5 horas × 60 minutos/hora = 300 minutos.')

# Diapositiva 6: Caso de estudio (Parte A)
pdf.chapter_title('Diapositiva 6: Caso de estudio (Parte A)')
pdf.chapter_body(
    'Un vehículo tiene un consumo de 8 litros por 100 kilómetros. Convertir a millas por galón:'
)
pdf.chapter_body(
    '1. 100 km × (1 milla / 1.60934 km) = 62.1371 millas.\n'
    '2. 8 L × (1 galón / 3.78541 L) = 2.1134 galones.\n'
    'Resultado: 62.1371 millas / 2.1134 galones ≈ 29.39 mpg.'
)

# Diapositiva 7: Caso de estudio (Parte B)
pdf.chapter_title('Diapositiva 7: Caso de estudio (Parte B)')
pdf.chapter_body(
    'Un tanque de agua tiene una capacidad de 5000 litros. Convertir a metros cúbicos: '
    '5000 L × (1 m³ / 1000 L) = 5 m³.'
)

# Diapositiva 8: Referencias
pdf.chapter_title('Diapositiva 8: Referencias')
pdf.chapter_body(
    'Referencias:\n'
    'Brown, T. L., LeMay, H. E., Bursten, B. E., Murphy, C. J., & Woodward, P. M. (2014). '
    'Química, la ciencia central (12ª ed.). Pearson.\n'
    'AprendeU (Video sobre análisis dimensional).'
)

# Diapositiva 9: Enlace al video
pdf.chapter_title('Diapositiva 9: Enlace al video')
pdf.chapter_body('Coloca aquí el enlace de tu video subido a YouTube.')

# Guardar el archivo PDF
output_pdf_path = "Presentacion_Analisis_Dimensional_Prueba_Oral.pdf"
pdf.output(output_pdf_path)

print(f"Archivo PDF guardado como: {output_pdf_path}")
