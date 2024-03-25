### What's here?

Currently, I've completed several projects, including:

1. [**DocsaidKit**](https://github.com/DocsaidLab/DocsaidKit): It contains some of the small tools I use regularly, acting as a toolbox.
2. [**DocAligner**](https://github.com/DocsaidLab/DocAligner): This project provides document positioning functionality, mainly to locate the four corners of documents.
3. [**DocClassifier**](https://github.com/DocsaidLab/DocClassifier): This project is for calculating document similarity, inspired by my friend. He finished the initial development and feasibility verification, then passed the idea to me. I completed the details and published it here.
4. [**GmailSummary**](https://github.com/DocsaidLab/GmailSummary): This is a project that provides Gmail email summaries, integrating Gmail API and OpenAI API to summarize a large number of emails and push updates at a fixed time every day.

There are also some other items still in planning:

5. **DocsaidOCR**:

    When it comes to OCR, one must mention the industry leader: [**PaddleOCR**](https://github.com/PaddlePaddle/PaddleOCR). Their model performance is very good, and their feature coverage is also very comprehensive. Usually, no matter what problem you encounter, just take a look at their offerings, and you might find a solution. However, there are often issues with the correct recognition of Traditional Chinese characters. Moreover, they have adopted the unique PaddlePaddle framework, which causes inconvenience for someone like me, a PyTorch user.

    Therefore, a few years ago, following their guidance, I built from scratch a business document OCR solution for Traditional Chinese. Compared to other vendors in Taiwan, it was highly competitive. However, this system was bought out, and I can no longer use it. Years later, I have new thoughts on the same problems, so I plan to redesign the module architecture and use entirely new algorithms to do it all over again. This includes, but is not limited to, the following topics:

    - **TextDetector:** How to design a module that can detect text in multiple orientations? Can speed and accuracy be achieved simultaneously?
    - **TextRecognizer:** The original model only covered 30,000 ideographic characters of Chinese, Japanese, and Korean. Is it possible to expand to 100,000 characters? Where to find the data?
    - **DocVQA:** Facing a complex structured document, how should we design a module that can answer questions? How scalable should this module's design be? I have tried ChatGPT and followed the guidance of PaddleOCR before, but the results were not very good. How can it be improved?
    - **DocGenerator:** There are already many public datasets for text synthesis, but how to design an efficient business document synthesis module?
    - **HandWriting:** Handwriting recognition is a very interesting topic. The most famous dataset is MNIST, but it is too simple. What we need to consider is how to deal with the challenge of Chinese handwriting?
    - **TableAnalysis:** Table analysis has been a very difficult topic in recent years. I have made some attempts, including using AWS and Google's solutions, but their capabilities in parsing frameless and irregular tables are not sufficient. How can it be improved?

That being said, I think working on OCR has a relatively low cost-performance value. Because the problems you need to solve not only require coverage across multiple sub-domains, the workload is huge. However, in the commercial world, OCR products are plentiful, making it difficult to differentiate, and users do not care about those long-tail data, and they usually won't pay extra for it.

But these topics are still full of many unknowns, and as long as there are unknowns, that's reason enough for me to continue pushing forward.

In the future, all the knowledge I possess or interesting topics will be shared here.

By the way, I also have a project for recording daily development: [**blog**](https://github.com/DocsaidLab/blog), based on the open-source project Docusaurus by Facebook. I'm still figuring out a lot, especially since I don't usually work with front-end frameworks. So, the website doesn't have flashy functions, just some articles. The blog content is hosted at [docsaid.org](https://docsaid.org).

＊

In my opinion, a project's completeness isn't just about its functionality but also its documentation, tests, CI/CD, version control, and more.

I also must admit my forgetfulness, so I try my best to record everything I do.

Based on my philosophy, the basic structure to build a project should look like this:

  - How to build the model?
  - Is it well-built?
  - How to use the model?

This structure helps us better understand and discuss a project, as well as improve its use and development.

For example, to reproduce an experimental result, we must consider the working environment to ensure our discussions are based on the same foundation. That's why I introduced Docker training modules as a solution.

If you're not familiar with container technology, seeing my training code might be confusing:

<div align="center">

**What is this? It goes from bad to incomprehensible?**

</div>

But from my experience in this field (stepping into pitfalls), you'll find that C++, CUDA, ONNX, Python, and PyTorch are all pitfalls, not to mention setting them up on Linux, Windows, macOS. If you don't learn Docker, you'll find life full of pitfalls. ~~(Is there a chance that Docker is also a pitfall?)~~

Another example is about abstracting our model training architecture. We can describe our model with a simple `YAML` file, separating the model's structure from the training parameters for better management. We can divide the model into several structures, like Backbone, Neck, Head, Loss, Metric. Through such abstraction, we can better understand our model and train it more effectively.

The last example concerns what happens after training the model.

During the training process, we might use many loss functions, optimizers, and model branches, but the inference stage is completely different. The simplest example is: you can't directly use the training ckpt file in a production environment, right? (Or can you?) Anyway, you'd need to package it with an inference framework, like ONNX or TorchScript.

Therefore, besides completing model training, we also provide a simple inference model, making it easier for you to use the functionalities we offer.

＊

Although I'm a native Chinese speaker, I prioritize English documentation in the projects I provide, as the main leaders in this industry communicate in English. Honestly, I'm not particularly good at writing documentation, so if you find any issues with my documents, please feel free to point them out. I'd be happy to improve them.

If you prefer to read in Chinese, I've compiled the same content together. You can find it by selecting "Chinese" from the top left corner of the README.
