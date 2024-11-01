from PyPDF2 import PdfReader, PdfWriter


file_innovations = "/mnt/data/Matriz - Final - _Innovations Matrix.pdf"
file_literature_review = "/mnt/data/Matriz - Final - _Literature review Matrix.pdf"


reader_innovations = PdfReader(file_innovations)
reader_literature_review = PdfReader(file_literature_review)

writer = PdfWriter()
for page in reader_innovations.pages:
    writer.add_page(page)

for page in reader_literature_review.pages:
    writer.add_page(page)


output_path = "/mnt/data/Combined_Matrix_Document.pdf"

with open(output_path, "wb") as output_pdf:
    writer.write(output_pdf)

output_path
