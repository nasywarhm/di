# Membuat diagram alir dengan simbol yang benar mengikuti standar flowchart
fig, ax = plt.subplots(figsize=(10, 14))

# Definisikan properti untuk kotak dan simbol diagram alir
process_box_props = dict(boxstyle="round,pad=0.3", facecolor="lightblue", edgecolor="black", lw=2)
decision_box_props = dict(boxstyle="diamond,pad=0.3", facecolor="lightgreen", edgecolor="black", lw=2)
terminator_box_props = dict(boxstyle="round,pad=0.5", facecolor="lightcoral", edgecolor="black", lw=2)
info_props = dict(boxstyle="round,pad=0.3", facecolor="lightgray", edgecolor="black", lw=1.5)

# Menggambar awal proses
ax.text(0.5, 0.95, "Mulai\nProduksi Tempe", ha="center", bbox=terminator_box_props, fontsize=10)

# Tahap 1: Pemilihan Kedelai (Proses)
ax.text(0.5, 0.85, "Pemilihan Kedelai\n(2 ton kedelai mentah)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.85, "Kedelai bersih\n2 ton (100%)", ha="left", bbox=info_props, fontsize=9)

# Tahap 2: Pencucian (Proses)
ax.text(0.5, 0.75, "Pencucian\n(2 ton kedelai, 2000 L air)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.75, "600 kg kedelai\nkotoran 0,02%", ha="left", bbox=info_props, fontsize=9)

# Tahap 3: Perendaman I (Proses)
ax.text(0.5, 0.65, "Perendaman I\n(600 kg kedelai, 1000 L air, 2 jam)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.65, "600 kg kedelai basah", ha="left", bbox=info_props, fontsize=9)

# Tahap 4: Perebusan (Proses)
ax.text(0.5, 0.55, "Perebusan\n(1000 L air, 2 jam, 605 kg kedelai)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.55, "605 kg kedelai rebus", ha="left", bbox=info_props, fontsize=9)

# Tahap 5: Perendaman II (Proses)
ax.text(0.5, 0.45, "Perendaman II\n(1000 L air)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.45, "607 kg kedelai\npH lebih rendah", ha="left", bbox=info_props, fontsize=9)

# Tahap 6: Pendinginan (Proses)
ax.text(0.5, 0.35, "Pendinginan\n(1000 L air, 608 kg kedelai, semalam)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.35, "608 kg kedelai\nsiap diproses", ha="left", bbox=info_props, fontsize=9)

# Tahap 7: Penirisan dan Penggilingan (Proses)
ax.text(0.5, 0.25, "Penirisan dan Penggilingan\n(600 kg kedelai)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.25, "600 kg kedelai\nsiap difermentasi", ha="left", bbox=info_props, fontsize=9)

# Tahap 8: Pencucian & Pemisahan Kulit Ari (Proses)
ax.text(0.5, 0.15, "Pencucian & Pemisahan Kulit Ari\n(590 kg kedelai)", ha="center", bbox=process_box_props, fontsize=10)
ax.text(0.85, 0.15, "590 kg kedelai bersih", ha="left", bbox=info_props, fontsize=9)

# Tahap 9: Peragian (Proses)
ax.text(0.5, 0.05, "Peragian\n(2 kg ragi untuk 590 kg kedelai)", ha="center", bbox=process_box_props, fontsize=10)

# Menghubungkan proses dengan panah
for i in range(8):
    ax.annotate('', xy=(0.5, 0.75 - i * 0.1), xytext=(0.5, 0.85 - i * 0.1),
                arrowprops=dict(facecolor='black', arrowstyle='->'))

# Akhir proses
ax.text(0.5, -0.05, "Tempe Jadi", ha="center", bbox=terminator_box_props, fontsize=10)

# Hubungkan ke akhir proses
ax.annotate('', xy=(0.5, 0.05), xytext=(0.5, 0.15),
            arrowprops=dict(facecolor='black', arrowstyle='->'))

# Bersihkan sumbu
ax.set_axis_off()

# Tampilkan diagram
plt.show()
