The goal of our API strategy is to give us a shared understanding of how we should build our API platform and how this should help us in achieving market success with our API products.

This strategy is developed and maintained by @a-akimov (Head of API Platform at Monite), but any feedback and contributions are always welcome.

## 1. We are API First

Monite is an [API-First company](https://swagger.io/resources/articles/adopting-an-api-first-approach/), meaning that we deliver our product to partners primarily through our API. This enables our partners to seamlessly integrate with our platform and embed our functionality into their existing user interfaces – our core value proposition.

As a result of this approach, whenever we introduce new capabilities to our product, we always begin with the API – considering its appearance, design for optimal developer experience with our partners, coherence with our overall API design, and more. Only after finalizing this vision and requirements do we proceed with implementing the API changes.

## 2. We treat API as a Product

As an API-First company, we place significant emphasis on the quality of our API, its development process, usage by our partners, and continuous improvement based on their feedback. This approach leads us to treat our [API as a Product](https://nordicapis.com/what-is-an-api-as-a-product/) in itself. It is a meta-product that combines the efforts of all teams, representing a single API integration layer.

Our API is not merely an extension of our product; it is the product itself, serving as its face. If certain functionality has been developed internally but not exposed in our API, it effectively does not exist for our customers.

## 3. We thoroughly design our API

API design greatly impacts the integration experience of our customers and their overall impression of our product. To achieve the best API design, we adhere to the following best practices in our work:

* We always begin any change in an API with discussing and approving its design, making us an **API Design First** company as well.

* We base our API design processes and tooling on the [OpenAPI Specification](https://www.openapis.org/), currently recognized as the best industry standard for API contracts for most types of Web APIs.

* We adopt a federated API design approach, where most teams develop API suggestions independently and then receive assistance and final approval from the **API Council** – a team of API design experts distributed across the organization.

* We maintain an [API style guide](https://github.com/team-monite/api-style-guide) that we apply to every API we design. Our goal is to automate this style guide as soon as possible and evolve it over time based on our enhanced understanding of API design.

## 4. We design our API to be flexible and evolvable

Although we thoroughly design our API, we aim to stay lean and agile. This mindset enables us to treat our API as a product, listen to our customers, and quickly adapt to their requirements and our evolving go-to-market strategy.

As a startup, not a corporate entity, we prioritize moving fast. We acknowledge that we may not yet know all the details of the product we are building, which means we will inevitably make mistakes. The key to overcoming these mistakes is understanding that we can fix them swiftly – adapt and evolve.

This approach influences how we design and build our APIs, ensuring they support evolvability from Day 1. In practice, this involves techniques such as API versioning, preferring nested structures over flattened ones, favoring enums over booleans, and designing open-ended use cases instead of rigid ones.

Designing a highly evolvable API is a complex skill that demands practice and collaboration.

## 5. We design a single API, not many APIs

When defining an API, some may argue that every web service, endpoint, or even each field of a request/response body is an API. Others might claim that every product produced by a company has a corresponding API. Although there is no right or wrong approach, defining numerous granular APIs can pose significant challenges for our customers, and here's why.

When our customers integrate with us, they typically have a set of use cases to implement. Often, these use cases involve different parts of our API platform, combining various resources, endpoints, and even products. However, during integration, customers aren't concerned with whether we define these as separate APIs. What truly matters to them is the ease and logic behind "gluing" all these parts together to cater to their use cases.

Internally, we can build as many services as we want and design our system architecture with any cross-cutting concerns that make sense for us. However, we must avoid exposing this architecture externally through our API designs. Once we start doing so, any change in the internal architecture will also necessitate a change in customer integrations. This consequence, known as one of the most negative effects of [Conway’s Law](https://martinfowler.com/bliki/ConwaysLaw.html), significantly [impacts API design](https://nordicapis.com/conways-law-what-does-it-mean-for-your-api-strategy/).

To circumvent this issue, we should always design a single API. This approach allows us to organically achieve consistency across all its parts, provide a unified developer experience, and blur the boundaries between different aspects of our product(s). As a result, we gain more flexibility to evolve our API without affecting customer integrations.

## 6. We make choices that are familiar to developers who use our API

The human brain and consciousness function by continuously analyzing patterns and comparing current situations to previous experiences. When a situation appears familiar, humans can make decisions and progress more rapidly. This concept underlies the desire for consistent and predictable usability patterns, whether in UX/UI or developer experience with APIs.

In practice, this principle translates to a simple approach: when making API design choices, we should analyze the best and most common practices for addressing specific problems in the tech industry and prefer solutions that are widespread and familiar to other developers.

If REST is the most prevalent API architecture style, we adhere to REST. If OAuth 2.0 is widely adopted and proven to be secure and reliable, we opt for OAuth 2.0. This approach is not only beneficial because it is familiar to many developers, but also because there is an extensive ecosystem of standards, tools, and technical content on applying such patterns in real-life applications.

While adopting new technologies may seem attractive, striking a balance between their appeal and maturity is crucial.

Reinventing the wheel can often be perceived as innovation, which is frequently accurate. However, each time we choose to do things differently, we must analyze and accept the effort required for us and our clients to adopt this new approach.

## 7. Follow the YAGNI principle when designing API

In general, our APIs should only expose what is truly necessary for our API clients. This crucial best practice allows us to maintain a minimal API surface – one that is easier to document, maintain, monitor, and protect – based on the actual use cases of our API clients.

This practice is commonly referred to as the [YAGNI principle](https://martinfowler.com/bliki/Yagni.html) and is often complemented by Postel's Law ([Robustness Principle](https://en.wikipedia.org/wiki/Robustness_principle)): “Be conservative in what you send, be liberal in what you accept.”

In practice, this means our APIs should not expose resources, parameters, actions, headers, or data unless it is clear why and how they will be used.

Note however, we cannot expect that our API clients will adhere to the same principle. Therefore, we must design our API to be tolerant of accepting inputs that are not part of the API contract.

## 8. Think about full end-to-end integration experience

API design is not limited to the appearance and behavior of backend APIs. In fact, many other components significantly impact the overall integration experience for partner developers.

Some examples of additional aspects to consider include:

* The design of our client-side SDKs: how they are designed, the naming conventions used, how well they integrate with our APIs, and their adherence to best development practices relevant to their programming languages and frameworks.

* The overall architecture choices our customers must make due to the design of our integration. This may include data storage and retrieval architectures, asynchronous processes and techniques like webhooks and web sockets, client-server communication, rate limiting, idempotency, and more.

* All the integration assets that assist our customers' developers in integrating with us and making specific choices. These assets primarily include a comprehensive and interactive Developer Portal, followed by API references, Postman collections, GitHub examples, videos, tutorials, and so on.

## 9. Improve based on feedback

The true potency of an API becomes evident only when it's leveraged by a diverse set of clients to craft functional applications and address real-world challenges. An effective API is architected such that its fundamental components are versatile enough to address a broad spectrum of issues within the same domain. However, crafting an impeccable API right from the start is an exceptionally challenging task.

This underlines the critical importance of maintaining a continual feedback mechanism from API clients, enabling the evolution and enhancement of the API's design and execution. With Hyrum's Law in mind, which states that an API creator cannot foresee all the ways their API will be utilized by clients, it becomes even more vital to collect and scrutinize feedback from the clients engaging with the API.

Feedback is a multifaceted concept and should be obtained through a variety of channels, such as feedback forms, surveys, in-person discussions, and data analytics. Additionally, it should not be confined solely to the design of the API, but should extend to cover all aspects including its documentation, performance, reliability, various integration resources, operational excellence, and beyond.

## 10. Strive to make our internal APIs as good as public

Numerous businesses tend to concentrate their primary API governance strategies on managing public/partner APIs, often providing internal teams more liberty and less oversight when developing private APIs. The principal motivations behind this approach include:

* Modifying an internal API is typically easier compared to a public one, where extended support periods for API clients may be necessary.

* The sheer volume of internal APIs is generally much higher, presenting a formidable challenge for effective governance.

Nevertheless, we identify considerable benefits in applying the same rules to our internal APIs as we do to our public ones. This approach not only simplifies potential future publication of parts of our internal APIs, but it also establishes a high standard of API quality across all teams.