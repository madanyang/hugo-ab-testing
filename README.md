# Hugo A/B Testing

## Motivation

A/B testing is a powerful technique for optimizing web experiences by comparing two versions of a webpage to determine which performs better. This Hugo A/B testing implementation provides a robust, flexible solution for:

- **Data-Driven Decision Making**: Move beyond guesswork to make informed design and content choices
- **Continuous Improvement**: Systematically refine website performance
- **User Experience Optimization**: Understand what resonates with your audience

## How It Works

Our Hugo A/B testing solution leverages Hugo's output formats and template system to create multiple page variants:

```yaml
# Key Configuration Concept
outputs:
  home:
    - HTML      # Control Version
    - TESTHTML  # Test Version
```

### Key Components
- **Multiple Output Formats**: Generate different page versions
- **Flexible Templates**: Create distinct variants
- **Verification Script**: Ensure correct implementation

## Getting Started

### Prerequisites
- Hugo (Extended Version Recommended)
- Basic understanding of Hugo templating

### Installation Steps

1. Clone the repository
2. Configure output formats in `config.yaml`
3. Create variant templates
4. Run verification script

```bash
# Verify AB Testing Configuration
.bin/verify
```

## Best Practices

- **Focus on One Variable**: Change only one element at a time
- **Statistical Significance**: Collect enough data
- **Clear Hypothesis**: Define expected outcomes
- **Consistent Metrics**: Use standardized measurement

## Potential Enhancements

1. **Analytics Integration**
   ```html
   <script>
     // Track A/B Test Variant
     window.abVersion = '{{ .OutputFormat.Name }}';
   </script>
   ```

2. **Randomized Variant Selection**
   ```go
   {{ $variants := slice "index.html" "index.testhtml.html" }}
   {{ $selectedVariant := index $variants (mod (now.Unix) (len $variants)) }}
   ```

3. **Persistent User Experience**
   - Maintain consistent variant for individual users
   - Use cookies for variant assignment

## Analyzing Results

### Metrics to Consider
- Conversion Rate
- Time on Page
- Bounce Rate
- User Engagement

### Recommended Tools
- Google Analytics
- Hugo-compatible tracking scripts
- Custom analytics integrations

## Contributing

Contributions are welcomed.

## License

This project is licensed under the [MIT License](LICENSE).

## Support

For questions or support, please [create an issue](https://github.com/madanyan/hugo-ab-testing/issues) in the repository.

This README provides an overview of the Hugo A/B testing implementation, including the motivation, how it works, key components, best practices, and potential enhancements. The project structure and example code files are also provided for easy reference.
