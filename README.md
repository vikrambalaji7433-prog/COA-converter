<!-- Save as assets/animated-title.svg -->
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 900 140" width="900" height="140" role="img" aria-labelledby="title">
  <title id="title">COA Converter - Animated Title</title>

  <!-- background -->
  <defs>
    <linearGradient id="g1" x1="0" x2="1">
      <stop offset="0" stop-color="#00d4ff"/>
      <stop offset="0.5" stop-color="#6a00ff"/>
      <stop offset="1" stop-color="#ff6a88"/>
    </linearGradient>

    <!-- glow filter -->
    <filter id="glow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="6" result="blur"/>
      <feMerge>
        <feMergeNode in="blur"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <!-- moving mask for "shimmer" -->
    <linearGradient id="shine" x1="0" x2="1">
      <stop offset="0" stop-color="white" stop-opacity="0"/>
      <stop offset="0.45" stop-color="white" stop-opacity="0.4"/>
      <stop offset="0.5" stop-color="white" stop-opacity="0.9"/>
      <stop offset="0.55" stop-color="white" stop-opacity="0.4"/>
      <stop offset="1" stop-color="white" stop-opacity="0"/>
    </linearGradient>
    <mask id="m">
      <!-- full rect but gradient will define the mask shape -->
      <rect x="0" y="0" width="100%" height="100%" fill="url(#shine)"/>
    </mask>

    <!-- subtle wave used for clipping -->
    <path id="wave" d="M0 40 C 120 0 260 80 420 40 C 560 0 700 80 900 40 L 900 140 L 0 140 Z"/>
  </defs>

  <!-- background panel -->
  <rect x="0" y="0" width="900" height="140" rx="12" fill="#0b0f1a"/>

  <!-- animated gradient title text -->
  <g transform="translate(40,88)">
    <text font-family="Segoe UI, Roboto, Arial, sans-serif"
          font-size="48"
          font-weight="700"
          letter-spacing="1"
          filter="url(#glow)"
          fill="url(#g1)">
      <tspan id="t1">COA Converter</tspan>
    </text>

    <!-- shimmer mask clipped to text -->
    <g mask="url(#m)">
      <text font-family="Segoe UI, Roboto, Arial, sans-serif"
            font-size="48"
            font-weight="700"
            letter-spacing="1"
            fill="white"
            fill-opacity="0.12">
        <tspan>COA Converter</tspan>
      </text>
    </g>

    <!-- small animated subtitle -->
    <text x="0" y="46" font-family="Segoe UI, Roboto, Arial, sans-serif"
          font-size="14" fill="#bcd2ff" opacity="0.9">
      Convert • Analyze • Export
      <animate attributeName="opacity" values="0;0.9;0" dur="4s" repeatCount="indefinite"/>
    </text>
  </g>

  <!-- sliding shimmer animation: animate the gradient's x offset via a rect that moves -->
  <rect x="-300" y="0" width="300" height="140" fill="url(#shine)" opacity="0.6">
    <animate attributeName="x" from="-300" to="1200" dur="2.6s" repeatCount="indefinite"/>
  </rect>

  <!-- decorative wave that slowly moves -->
  <g opacity="0.18" transform="translate(0,0)">
    <use href="#wave" fill="#ffffff"/>
    <animateTransform attributeName="transform"
                      type="translate"
                      values="0,0; -30,0; 0,0"
                      dur="6s" repeatCount="indefinite"/>
  </g>

  <!-- small pulsing badge on right -->
  <g transform="translate(760,20)">
    <circle r="20" fill="#00d4ff"/>
    <circle r="20" fill="#00d4ff" opacity="0.6">
      <animate attributeName="r" values="18;28;18" dur="1.6s" repeatCount="indefinite"/>
      <animate attributeName="opacity" values="1;0.2;1" dur="1.6s" repeatCount="indefinite"/>
    </circle>
    <text x="-9" y="7" font-family="Segoe UI, Roboto, Arial, sans-serif" font-size="14" fill="#041028">v1</text>
  </g>

  <!-- accessibility: invisible live text (optional) -->
  <desc>Animated header for the COA Converter project.</desc>
</svg>
