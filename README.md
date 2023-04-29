# SlideCraft

Generate AI crafted slidedecks from PDF content


## Planning

Given filepath to PDF document:
    - Extract text from pdf
    - Summarize with OpenAI (use summary of summaries method for managing context length
      limits)
    - Take summary and prompt to create remark.js slideshow from it
        - Include embedded prompts for stable diffusion generated images
        - Extract image prompts, generate images, insert into remark.js slideshow
    - Render slideshow and save as PDF
    - Initially, output PDF to disk
        - Extension: upload result to s3, share downloadable link to it

Then, extend to accept documents to summarize from an API
    - Accept file uploads, save files to s3
    - Extend summarizer to read document from s3 source
    - Take final s3 link output and return as API response to trigger download to
      user

