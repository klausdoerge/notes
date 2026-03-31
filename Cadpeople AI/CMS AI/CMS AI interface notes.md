
We want a MCP for creating content directly inside the CMS. We should not try to fix this interface to a specific CMS, but rather have the LLM create structured data and instructions, which can be translated into CMS specific instructions for the MCP servers that the vendors are creating. This will ensure, that we are not focusing too much on a single vendor, and also enables us to work with our own format, which might include extra instructions we can use for other purposes.

We should make the LLM return a formatted answer we can us for a wide variety of purposes.

Example:

Create a simple example article about the moon

Return

{
	"subject" : "the moon",
	"original-question" : "Create a simple example article about the moon",
	"date-created" : "some-date",
	"tags" : "moon, solar-system, planets, earth ...",
	"response" : "llm-response-text",
	"...."
}

- Maye we are able to generate images from the content
- Maybe we should be able to generate a quiz, based on the assumed knowledge of the user asking the question
- Generate a video? maybe search a media-library of pre-makde-videos instead... generally this might be good, to ensure that the quality of the service stays valid and is not 100% auto-generated.

The resulting data-set should be enough to create articles in any CMS and also use the response-data for training and similarity searches from other requests.. maybe a user should be able to modify the result, to ensure that other users asking the same question, will get a proper reponse.

Maybe connect with Knowledge base

