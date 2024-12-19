# Copyright Information
This is Wenzhi Bai's academic website, powered by Jekyll & AcademicPages, a fork of Minimal Mistakes. My repository is forked from the [Academic Pages template](https://github.com/academicpages/academicpages.github.io). Academic Pages is a GitHub Pages template for academic websites and is under the MIT license. My information is copyrighted by myself with all rights reserved to the extent of applicable law.

# Maintenance
## Bugfixes and Enhancements
See more info at https://academicpages.github.io/

## Modifying Content
1. Set site-wide configuration in `_config.yml`.
1. Update the links at the top of the page in `_data/navigation.yml`, followed by adjusting it from the `collections` tag in `_config.yml`.
1. Upload any files (like PDFs, .zip files, etc.) to the `files/` directory. They will appear at https://wenzhibai.github.io/files/example.pdf.
1. Upload any images to the `images/` directory. They will appear at https://wenzhibai.github.io/images/example.png.
1. Use the Jupyter notebooks or Python scripts in the `markdown_generator` folder to generate markdown files for publications and talks from a TSV file.

## Running Locally
1. Start Docker.

2. Build the container:
```bash
docker build -t jekyll-site .
```

3. Run the container:
```bash
docker run -p 4000:4000 --rm -v $(pwd):/usr/src/app jekyll-site
# -p 4000:4000: Maps port 4000 on your host to port 4000 in the container.
# --rm: Automatically removes the container when it exits.
# -v $(pwd):/usr/src/app: Mounts the current directory to /usr/src/app in the container.
```

4. Use the following address to preview:
[http://localhost:4000/](http://localhost:4000/) or [http://0.0.0.0:4000/](http://0.0.0.0:4000/)

## Deployment
1. Commit any modifications and push to the origin.
1. Check status by going to the repository settings, in the "GitHub Pages" section.
1. Review at https://wenzhibai.github.io/
