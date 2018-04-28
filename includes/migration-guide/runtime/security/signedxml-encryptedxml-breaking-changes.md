### <a name="signedxml-and-encryptedxml-breaking-changes"></a><span data-ttu-id="f0f83-101">Cambios importantes en SignedXml y EncryptedXml</span><span class="sxs-lookup"><span data-stu-id="f0f83-101">SignedXml and EncryptedXml Breaking Changes</span></span>

|   |   |
|---|---|
|<span data-ttu-id="f0f83-102">Detalles</span><span class="sxs-lookup"><span data-stu-id="f0f83-102">Details</span></span>|<span data-ttu-id="f0f83-103">En .NET Framework 4.6.2, las revisiones de seguridad de <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> y <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> generan otros comportamientos en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f0f83-103">In .NET Framework 4.6.2, Security fixes in <xref:System.Security.Cryptography.Xml.SignedXml?displayProperty=name> and <xref:System.Security.Cryptography.Xml.EncryptedXml?displayProperty=name> lead to different run-time behaviors.</span></span> <span data-ttu-id="f0f83-104">Por ejemplo,</span><span class="sxs-lookup"><span data-stu-id="f0f83-104">For example,</span></span><ul><li><span data-ttu-id="f0f83-105">Si un documento tiene varios elementos con el mismo atributo <code>id</code> y una firma está destinada a uno de esos elementos como la raíz de la firma, el documento ahora se considerará no válido.</span><span class="sxs-lookup"><span data-stu-id="f0f83-105">If a document has multiple elements with the same <code>id</code> attribute and a signature targets one of those elements as the root of the signature, the document will now be considered invalid.</span></span></li><li><span data-ttu-id="f0f83-106">Los documentos con algoritmos de transformación de XPath no canónicos en las referencias ahora se consideran no válidos.</span><span class="sxs-lookup"><span data-stu-id="f0f83-106">Documents using non-canonical XPath transform algorithms in references are now considered invalid.</span></span></li><li><span data-ttu-id="f0f83-107">Los documentos con algoritmos de transformación de XSLT no canónicos en las referencias ahora se consideran no válidos.</span><span class="sxs-lookup"><span data-stu-id="f0f83-107">Documents using non-canonical XSLT transform algorithms in references are now consider invalid.</span></span></li><li><span data-ttu-id="f0f83-108">Los programas que usen firmas separadas de recurso externo no podrán hacerlo.</span><span class="sxs-lookup"><span data-stu-id="f0f83-108">Any program making use of external resource detached signatures will be unable to do so.</span></span></li></ul>|
|<span data-ttu-id="f0f83-109">Sugerencia</span><span class="sxs-lookup"><span data-stu-id="f0f83-109">Suggestion</span></span>|<span data-ttu-id="f0f83-110">Es posible que los desarrolladores quieran revisar el uso de <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> y <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, así como los tipos derivados de <xref:System.Security.Cryptography.Xml.Transform>, ya que es posible que un receptor de documentos no pueda procesarlo.</span><span class="sxs-lookup"><span data-stu-id="f0f83-110">Developers might want to review the usage of <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform> and <xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform>, as well as types derived from <xref:System.Security.Cryptography.Xml.Transform> since a document receiver may not be able to process it.</span></span>|
|<span data-ttu-id="f0f83-111">Ámbito</span><span class="sxs-lookup"><span data-stu-id="f0f83-111">Scope</span></span>|<span data-ttu-id="f0f83-112">Secundaria</span><span class="sxs-lookup"><span data-stu-id="f0f83-112">Minor</span></span>|
|<span data-ttu-id="f0f83-113">Versión</span><span class="sxs-lookup"><span data-stu-id="f0f83-113">Version</span></span>|<span data-ttu-id="f0f83-114">4.6.2</span><span class="sxs-lookup"><span data-stu-id="f0f83-114">4.6.2</span></span>|
|<span data-ttu-id="f0f83-115">Tipo</span><span class="sxs-lookup"><span data-stu-id="f0f83-115">Type</span></span>|<span data-ttu-id="f0f83-116">Tiempo de ejecución</span><span class="sxs-lookup"><span data-stu-id="f0f83-116">Runtime</span></span>|
|<span data-ttu-id="f0f83-117">API afectadas</span><span class="sxs-lookup"><span data-stu-id="f0f83-117">Affected APIs</span></span>|<ul><li><xref:System.Security.Cryptography.Xml.Transform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXPathTransform?displayProperty=nameWithType></li><li><xref:System.Security.Cryptography.Xml.XmlDsigXsltTransform?displayProperty=nameWithType></li></ul>|
