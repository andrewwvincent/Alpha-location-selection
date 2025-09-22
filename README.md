# US School Location Analysis Tool

An interactive web application for analyzing optimal school locations across the United States using enrollment prediction models.

## 🎯 Features

- **Interactive US Map**: View 14,448+ schools nationwide with tuition-based color coding
- **Real-time Analysis**: Adjust tuition, scaling factors, and distance parameters with live feedback
- **Census Tract Analysis**: Click tracts to see detailed enrollment predictions
- **Metro Navigation**: Jump to 40+ major metropolitan areas
- **State-by-State Loading**: Load census tract data for specific states on demand

## 🎛️ Interactive Controls

### Tuition Slider ($15K - $80K)
- Adjust proposed tuition levels in real-time
- See immediate impact on enrollment predictions
- Formatted display with thousands separators

### Tuition Scaling Factor (10% - 50%)
- Controls minimum tuition threshold for school contributions
- Default: 25% (schools with tuition ≥ 25% of proposed contribute)

### Distance Range (Dual Slider)
- **Min Distance**: 1-25 miles (default: 5 miles)
- **Max Distance**: 5-30 miles (default: 20 miles)
- Visual track shows active range between handles

## 🗺️ How to Use

1. **Open the Application**: Load `index.html` in your web browser
2. **Navigate**: Use the metro dropdown to jump to major cities
3. **Load Data**: Check states in the selector and click "Load Selected States"
4. **Analyze**: Adjust sliders to see real-time enrollment predictions
5. **Explore**: Click census tracts for detailed school contribution analysis

## 📊 Data Sources

- **Schools**: 14,448 schools across all US states with enrollment and tuition data
- **Census Tracts**: Currently includes Massachusetts (MA.geojson)
- **Metro Areas**: 40+ major metropolitan areas for quick navigation

## 🚀 GitHub Pages Deployment

### Quick Deploy
1. Upload all files to a GitHub repository
2. Enable GitHub Pages in repository settings
3. Select "Deploy from a branch" → main branch
4. Your app will be available at: `https://yourusername.github.io/repositoryname`

### File Structure
```
Final App/
├── index.html              # Main application
├── us_schools_data.js       # School data (14,448 schools, ~2MB)
├── census_tracts/
│   └── MA.geojson          # Massachusetts census tracts (~6MB)
└── README.md               # This file
```

## 🔧 Technical Details

### Performance Optimizations
- **Lazy Loading**: Census tracts load only when states are selected
- **Caching**: Enrollment scores cached to prevent recalculation
- **Progressive Enhancement**: Works with or without census tract data

### Browser Compatibility
- Modern browsers with JavaScript enabled
- Responsive design for desktop and mobile
- Uses Leaflet.js for mapping functionality

## 📈 Model Details

The enrollment prediction model uses:
- **Distance Scaling**: Linear decay from min to max distance
- **Tuition Scaling**: Schools with higher tuition contribute more
- **Enrollment Weighting**: Larger schools have greater impact
- **Geographic Constraints**: Only schools within distance range contribute

## 🎨 Color Coding

### School Markers (by tuition)
- 🟢 **Sea Green**: < $10K
- 🟢 **Lime Green**: $10K-$20K  
- 🟡 **Gold**: $20K-$30K
- 🟠 **Orange**: $30K-$40K
- 🔴 **Red**: $40K+

### Census Tracts (by enrollment score)
- 🔴 **Red**: 5000+ (highest demand)
- 🟡 **Yellow**: 2500-2999 (key threshold)
- 🟢 **Green**: 1000-1499
- 🔵 **Blue**: 0-49 (lowest demand)

## 📝 Future Enhancements

- Add census tract data for all 50 states
- Implement demographic overlays
- Add export functionality for analysis results
- Include market saturation indicators

## 🤝 Contributing

This tool was developed for strategic school location planning. For questions or enhancements, please open an issue in the repository.

---

**Built with**: HTML5, CSS3, JavaScript, Leaflet.js  
**Data**: US Census Bureau, School location databases  
**Deployment**: GitHub Pages ready
