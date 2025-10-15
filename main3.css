// Realistic Rose Drawing with Canvas API

const canvas = document.createElement('canvas');
canvas.width = 500;
canvas.height = 500;
document.body.appendChild(canvas);
const ctx = canvas.getContext('2d');

// Helper: Draw a petal
function drawPetal(cx, cy, r, angle, color) {
    ctx.save();
    ctx.translate(cx, cy);
    ctx.rotate(angle);
    ctx.beginPath();
    ctx.moveTo(0, 0);
    ctx.bezierCurveTo(r * 0.5, -r * 0.2, r, r * 0.8, 0, r);
    ctx.bezierCurveTo(-r, r * 0.8, -r * 0.5, -r * 0.2, 0, 0);
    ctx.closePath();
    ctx.fillStyle = color;
    ctx.shadowColor = "#b22222";
    ctx.shadowBlur = 10;
    ctx.fill();
    ctx.restore();
}

// Draw rose center
function drawCenter(cx, cy, r) {
    ctx.save();
    ctx.beginPath();
    ctx.arc(cx, cy, r, 0, 2 * Math.PI);
    ctx.fillStyle = "#c2185b";
    ctx.shadowColor = "#ad1457";
    ctx.shadowBlur = 15;
    ctx.fill();
    ctx.restore();
}

// Draw stem
function drawStem(cx, cy, length) {
    ctx.save();
    ctx.beginPath();
    ctx.moveTo(cx, cy);
    ctx.bezierCurveTo(cx + 10, cy + length / 2, cx - 10, cy + length / 2, cx, cy + length);
    ctx.lineWidth = 8;
    ctx.strokeStyle = "#388e3c";
    ctx.shadowColor = "#2e7d32";
    ctx.shadowBlur = 8;
    ctx.stroke();
    ctx.restore();
}

// Draw leaves
function drawLeaf(cx, cy, angle, size) {
    ctx.save();
    ctx.translate(cx, cy);
    ctx.rotate(angle);
    ctx.beginPath();
    ctx.moveTo(0, 0);
    ctx.bezierCurveTo(size, -size / 2, size, size, 0, size);
    ctx.bezierCurveTo(-size, size, -size, -size / 2, 0, 0);
    ctx.closePath();
    ctx.fillStyle = "#43a047";
    ctx.shadowColor = "#2e7d32";
    ctx.shadowBlur = 6;
    ctx.fill();
    ctx.restore();
}

// Main rose drawing
function drawRose() {
    const cx = 250, cy = 200;
    // Draw stem
    drawStem(cx, cy + 40, 180);

    // Draw leaves
    drawLeaf(cx - 30, cy + 120, -0.5, 40);
    drawLeaf(cx + 30, cy + 160, 0.7, 35);

    // Draw petals (layers)
    const petalColors = [
        "#e57373", "#f06292", "#d81b60", "#c2185b"
    ];
    for (let layer = 0; layer < 4; layer++) {
        let petals = 8 + layer * 2;
        let radius = 40 + layer * 18;
        for (let i = 0; i < petals; i++) {
            let angle = (2 * Math.PI / petals) * i + (layer % 2) * 0.2;
            drawPetal(cx, cy, radius, angle, petalColors[layer]);
        }
    }
    // Draw center
    drawCenter(cx, cy, 28);
}

drawRose();
