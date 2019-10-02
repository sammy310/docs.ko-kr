---
ms.openlocfilehash: b965c3a975b0f2cadd906799fef1665261d96d6e
ms.sourcegitcommit: 55f438d4d00a34b9aca9eedaac3f85590bb11565
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2019
ms.locfileid: "71182051"
---
### <a name="envelopedcms-defaults-to-aes-256-encryption"></a><span data-ttu-id="0e2a8-101">EnvelopedCms를 기본적으로 AES-256 암호화로 설정</span><span class="sxs-lookup"><span data-stu-id="0e2a8-101">EnvelopedCms defaults to AES-256 encryption</span></span>

<span data-ttu-id="0e2a8-102">`EnvelopedCms`에서 사용하는 기본 대칭 암호화 알고리즘이 TripleDES에서 AES-256으로 변경되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-102">The default symmetric encryption algorithm used by `EnvelopedCms` has changed from TripleDES to AES-256.</span></span>

#### <a name="details"></a><span data-ttu-id="0e2a8-103">세부 정보</span><span class="sxs-lookup"><span data-stu-id="0e2a8-103">Details</span></span>

<span data-ttu-id="0e2a8-104">.Net Core 미리 보기 7 버전 이하에서 생성자 오버로드를 통해 대칭 암호화 알고리즘을 지정하지 않고 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms>가 데이터를 암호화하는 데 사용되는 경우 데이터가 TripleDES/3des/3DEA/DES3 알고리즘을 사용하여 암호화되었습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-104">In .NET Core Preview 7 and earlier versions, when <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> is used to encrypt data without specifying a symmetric encryption algorithm via a constructor overload, the data was encrypted with the TripleDES/3DES/3DEA/DES3-EDE algorithm.</span></span>

<span data-ttu-id="0e2a8-105">.Net Core 3.0 미리 보기 8부터( [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet 패키지의 버전 4.6.0을 통해) 기본 알고리즘이 현대화 알고리즘용 AES-256으로 변경되어 보안 기본 옵션을 개선합니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-105">Starting with .NET Core 3.0 Preview 8 (via version 4.6.0 of the [System.Security.Cryptography.Pkcs](https://www.nuget.org/packages/System.Security.Cryptography.Pkcs/) NuGet package), the default algorithm has been changed to AES-256 for algorithm modernization and to improve the security of default options.</span></span> <span data-ttu-id="0e2a8-106">메시지 받는 사람 인증서에 (EC가 아닌) Diffie-Hellman 공개 키가 있는 경우 기본 플랫폼의 제한 사항으로 인해 <xref:System.Security.Cryptography.CryptographicException>에서 암호화 작업이 실패할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-106">If a message recipient certificate has a (non-EC) Diffie-Hellman public key, the encryption operation may fail with a <xref:System.Security.Cryptography.CryptographicException> due to limitations in the underlying platform.</span></span>

<span data-ttu-id="0e2a8-107">다음 샘플 코드에서는 .NET Core 3.0마미리 보기 7 이전 버전에서 실행되는 경우 데이터가 TripleDES로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-107">In the following sample code, the data is encrypted with TripleDES if running on .NET Core 3.0 Preview 7 or earlier.</span></span> <span data-ttu-id="0e2a8-108">.NET Core 3.0 미리 보기 8 이상에서 실행되는 경우 데이터가 AES-256로 암호화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-108">If running on .NET Core 3.0 Preview 8 or later, it is encrypted with AES-256.</span></span>

```csharp
EnvelopedCms cms = new EnvelopedCms(content);
cms.Encrypt(recipient);
return cms.Encode();
```

#### <a name="version-introduced"></a><span data-ttu-id="0e2a8-109">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="0e2a8-109">Version introduced</span></span>

<span data-ttu-id="0e2a8-110">3.0 미리 보기 8</span><span class="sxs-lookup"><span data-stu-id="0e2a8-110">3.0 Preview 8</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="0e2a8-111">권장 작업</span><span class="sxs-lookup"><span data-stu-id="0e2a8-111">Recommended action</span></span>

<span data-ttu-id="0e2a8-112">이 변경으로 부정적인 영향을 받는 경우 다음과 같이 <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier> 형식의 매개 변수를 포함하는 <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> 생성자에서 암호화 알고리즘 식별자를 명시적으로 지정하여 TripleDES 암호화를 복원할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0e2a8-112">If you are negatively impacted by the change, you can restore TripleDES encryption by explicitly specifying the encryption algorithm identifier in an <xref:System.Security.Cryptography.Pkcs.EnvelopedCms> constructor that includes a parameter of type <xref:System.Security.Cryptography.Pkcs.AlgorithmIdentifier>, such as:</span></span>

```csharp
Oid tripleDesOid = new Oid("1.2.840.113549.3.7", null);
AlgorithmIdentifier tripleDesIdentifier = new AlgorithmIdentifier(tripleDesOid);
EnvelopedCms cms = new EnvelopedCms(content, tripleDesIdentifier);

cms.Encrypt(recipient);
return cms.Encode()l
```

#### <a name="category"></a><span data-ttu-id="0e2a8-113">범주</span><span class="sxs-lookup"><span data-stu-id="0e2a8-113">Category</span></span>

<span data-ttu-id="0e2a8-114">암호화</span><span class="sxs-lookup"><span data-stu-id="0e2a8-114">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="0e2a8-115">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="0e2a8-115">Affected APIs</span></span>

- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>
- <xref:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)?displayProperty=nameWithType>

<!--

### Affected APIs

- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.#ctor(System.Security.Cryptography.Pkcs.ContentInfo)`
- `M:System.Security.Cryptography.Pkcs.EnvelopedCms.%23ctor(System.Security.Cryptography.Pkcs.SubjectIdentifierType,System.Security.Cryptography.Pkcs.ContentInfo)`

-->
