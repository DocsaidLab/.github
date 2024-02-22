[English](./profile/README_en.md) | **[中文](./profile/README.md)**

<div align="center">
  <img src="https://github.com/DocsaidLab/.github/blob/main/cover.png" width="1000"/>
</div>

---

**Dear Reader,**

Welcome to DOCSAID's GitHub homepage.

I'm an AI engineer living in Taiwan and also the founder of this organization, Zephyr.

The reason behind establishing this organization is quite straightforward. It offers more enriched features than a personal account does, allowing me to invite like-minded friends to code together and explore interesting topics. Using a GitHub organization account brings more fascinating features without any additional cost (right?).

With so many advantages, why not create one for fun? Exactly my thought!

However, the most challenging part of this whole endeavor has been creating a logo for the organization. It's indeed a troublesome task. As an AI engineer, using Paint is already my limit. Although I've tried asking GPT to help me draw, it always ended up creating something bizarre. Eventually, after a bit of chaos, it turned into what you see now, and I hope you don't find it too strange.

＊

**DOCSAID** is a name composed of two words: "DOC" and "SAID". Since my work primarily revolves around text analysis, I wanted the organization's name to reflect this field. Essentially, it means:

<div align="center">

**The moment a document is created, it has already said what it wants to convey.**

</div>

So, what exactly did these documents say? Now, we just need to analyze them!

Interestingly, after finalizing the name, I realized it even contains the letters AI, which was a pleasant surprise.

＊

Analyzing documents is my daily job, including image text recognition, image fraud detection, topic classification, keyword extraction, and more. In my view, a document isn't just words; it could be an image, a video, a song, a dataset, or even a person's behavior. As long as there's analytical value or we're willing to analyze it, I believe everything can be considered a documents! (chaotic evil?)

So, how many people are in this organization?

Strictly speaking: None.

So far, I haven't formed any official partnerships; it's more like a diary etched with code.

But from a broader perspective, I do get some help from my friends who brainstorm ideas or write some code. In that sense, there are two or three free members. Maybe at some suitable moment in the future, they might decide to join or become co-founders to establish a larger organization, but that's for the future to decide.

### What's here?

Currently, I've completed several projects, including:

1. [**DocsaidKit**](https://github.com/DocsaidLab/DocsaidKit): It contains some of the small tools I use regularly, acting as a toolbox.
2. [**DocAligner**](https://github.com/DocsaidLab/DocAligner): This project provides document positioning functionality, mainly to locate the four corners of documents.
3. [**DocClassifier**](https://github.com/DocsaidLab/DocClassifier): This project is for calculating document similarity, inspired by my friend. He finished the initial development and feasibility verification, then passed the idea to me. I completed the details and published it here.

There are also some other items still in planning:

4. **DocsaidOCR**:

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

  - Introduction
  - Table of Contents
  - Quick Start (Model inference API)
  - Evaluate Model (Benchmark)
  - Train Model
  - Dataset Introduction
  - Dataset Preprocessing
  - Dataset Implementation
  - Build Training Environment
  - Execute Training (Based on Docker)
  - Convert Model to ONNX Format (Based on Docker)
  - Submit Dataset
  - FAQs
  - References

This structure helps us better understand and discuss a project, as well as improve its use and development.

For example, to reproduce an experimental result, we must consider the working environment to ensure our discussions are based on the same foundation. That's why I introduced Docker training modules as a solution. If you're not familiar with container technology, seeing my training code might be confusing:

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

### If you want to adjust the model?

This might be your most concerning topic.

Based on the topics I've defined and the models I provide, I believe we can solve most application scenarios. However, I also understand that some scenarios might require better model performance, necessitating the collection of your own dataset for model fine-tuning.

You might get stuck at this step, like most people do, but don't panic.

I've broadly categorized this issue into three plus one scenarios:

- **Scenario One: You know exactly what I'm doing:**

    In this case, you can directly fork my project and use your own dataset for model training. This way, you can achieve better model performance. If you encounter any issues during this process, feel free to raise them, and I'd be more than willing to resolve them.

- **Scenario Two: You know my project's functionality meets your needs, but you don't know how to adjust it:**

    In this scenario, you can directly send me an email with your requirements and the "dataset you want to solve". I can help you fine-tune the model, allowing you to achieve better model performance.

    It's free, but I can't be pressured for time, and I don't guarantee execution. (<== This is important!)

    Although I'm working on open-source projects, I'm not just doing this for fun. When the time comes, the model will naturally be updated, and you "might" get better model performance by just sending an email. Anyway, it can be considered a win-win situation, right?

- **Scenario Three: You want to develop a specific functionality:**

    Then, send me an email to discuss it. If I find it interesting, I'd be more than happy to help you develop it, but I hope you can prepare a dataset of a certain scale first. Even if I'm interested, I might not have the time to obtain enough data, or some special data might require special channels to acquire.

    This scenario is the same as the above; it's free, but I can't be pressured for time, and I don't guarantee execution.

    Note that the final result must be open-source, allowing more people to benefit. The ownership of the development project also fully belongs to me. Of course, I'll add you to the contributors section of the project documentation, and regardless of how I handle the project later, you'll retain the right to use it.

- **Scenario Four: When Rapid Development of a Specific Feature is Your Goal:**

    When time is of the essence, we can shift towards a commissioned development collaboration. Based on your requirements, I'll present a reasonable quote. The calculation is straightforward: the time I need to invest multiplied by my salary, plus some necessary development costs. How I manage to find people to help with the development is my concern.

    Taking the `DocAligner` project as an example, starting from scratch, according to my development pace, it normally requires a six-month development cycle. (In reality, because I was too engrossed, I completed it in just three months by working intensively), such a commissioned project would be quoted at around $25,000. This price encompasses the entire process from data collection, model training, to system deployment, just as you see.

    Additionally, you might overlook the "necessary costs" mentioned above, referring to training machines. I've worked on a facial recognition project before, where, with the dataset and machine ready, it took two months to complete a model. So, the development cost was roughly $8,000, but the cloud training machine rental fee amounted to $20,000 (a significant expense!), which is a cost that must be considered.

    Also, I won't accept proposals like: "I want to achieve XXX's LLM OOO functionality". While I am also skilled at building generative models, it's only on a small scale. Anything related to LLM often involves expenditures in the hundreds of millions. Currently, I remain a user, and as for training, I apologize for the inconvenience.

    It's important to note that even in commissioned development, the ownership of the project remains with me. I don't recommend buying out projects because it doesn't align with the principle of continuous progress. In the AI field, as technology advances, today's solutions might quickly become outdated. If you buy out a project, over time, you might find that this investment has lost its original value. But don't worry, the purpose of commissioned development is to swiftly meet your needs. If I succeed, it's a win-win outcome, and we can happily conclude the transaction. If not, consider it a lack of skill on my part, and I won't charge you any development fees, but if cloud machines are rented, that cost still needs to be covered. Although I can absorb the development costs myself, the expense of cloud machines is too high for me to bear, please understand.

    You might find the issue of project ownership perplexing.

    But give it some thought, and you might realize that you're just looking to "drink milk", not necessarily "own a cow".

    - How tiring is it to raise a cow? (You need to maintain engineers for the project)
    - It takes up space and is hard to care for. (Setting up training machines is expensive, renting cloud machines is pricey, and buying hardware often breaks)
    - It fears the cold and the heat. (Tuning models until you question your life choices)
    - And it might just die on you unexpectedly. (Failing to meet expected results)
    - Truly, it's a loss. (Spending money to buy out the project)

    If after careful consideration, you still insist on buying out the project, I won't stop you. I'll provide you with another quote, and we can still collaborate together.

＊

- **Please Note:**
  - **In all forms of development projects, I absolutely will not open source your data unless I have your permission.**
  - **Normally, the data will only be used to update the model.**
  - **Dataset submission: docsaidlab@gmail.com**

### In Conclusion

Finally, please remember, I'm an AI engineer, not a jack-of-all-trades. So, I won't do things I'm not good at, like front-end, back-end, databases, networking, etc. If you have such needs, I can only say: I might try to find the right person for you, but it's not guaranteed. The problem I'm best at solving is, given an input, to produce a specific output, and I can try my best to solve it with a model. Just like the projects I've open-sourced.

In this era, we are truly fortunate to have Google, OpenAI, Facebook, Microsoft, NVIDIA, and countless active open-source communities. From their open-source projects, we can draw a wealth of knowledge and learn cutting-edge technologies. I especially enjoy the feeling of navigating through the ocean of knowledge, especially in the field of deep learning, which amazes me with its beauty.

Every time I explore new technologies, it's like constantly getting new toys as a child, each discovery a gift of novelty and surprise. By sharing open-source projects, I hope to pass on this joy and knowledge to more people, letting us advance together in this field.

If you like my projects, don't be hesitate, go ahead and use them.

＊

2024, Zephyr
