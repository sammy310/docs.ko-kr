---
ms.openlocfilehash: 5c09bee92f679cd7e7a95cd23d5ce0ca9b57170c
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614743"
---
### <a name="wcf-transport-security-supports-certificates-stored-using-cng"></a><span data-ttu-id="e88f4-101">WCF 전송 보안이 CNG를 사용하여 저장한 인증서를 지원</span><span class="sxs-lookup"><span data-stu-id="e88f4-101">WCF transport security supports certificates stored using CNG</span></span>

#### <a name="details"></a><span data-ttu-id="e88f4-102">설명</span><span class="sxs-lookup"><span data-stu-id="e88f4-102">Details</span></span>

<span data-ttu-id="e88f4-103">.NET Framework 4.6.2를 대상으로 하는 앱부터, WCF 전송 보안에서 Windows 암호화 라이브러리(CNG)를 사용하여 저장한 인증서를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e88f4-103">Starting with apps that target the .NET Framework 4.6.2, WCF transport security supports certificates stored using the Windows Cryptography Library (CNG).</span></span> <span data-ttu-id="e88f4-104">이 지원은 지수 길이가 32비트 이하인 공개 키로 인증서로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88f4-104">This support is limited to certificates with a public key that has an exponent no more than 32 bits in length.</span></span> <span data-ttu-id="e88f4-105">애플리케이션이 .NET Framework 4.6.2를 대상으로 하는 경우 이 기능은 기본적으로 켜집니다. 이전 버전의 .NET Framework에서 CSG 키 스토리지 공급자와 함께 X509 인증서를 사용하려고 하면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="e88f4-105">When an application targets the .NET Framework 4.6.2, this feature is on by default.In earlier versions of the .NET Framework, the attempt to use X509 certificates with a CSG key storage provider throws an exception.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="e88f4-106">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="e88f4-106">Suggestion</span></span>

<span data-ttu-id="e88f4-107">.NET Framework 4.6.1 이전 버전을 대상으로 하지만 .NET Framework 4.6.2에서 실행 중인 앱은 app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 줄을 추가하여 CNG 인증서에 대한 지원을 사용하도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88f4-107">Apps that target the .NET Framework 4.6.1 and earlier but are running on the .NET Framework 4.6.2 can enable support for CNG certificates by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
  <AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableCngCertificates=false" />
</runtime>
```

<span data-ttu-id="e88f4-108">다음 코드를 사용하여 프로그래밍 방식으로 이 작업을 수행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e88f4-108">This can also be done programmatically with the following code:</span></span>

```csharp
private const string DisableCngCertificates = @"Switch.System.ServiceModel.DisableCngCertificate";

AppContext.SetSwitch(disableCngCertificates, false);
```

```vb
Const DisableCngCertificates As String = "Switch.System.ServiceModel.DisableCngCertificates"
AppContext.SetSwitch(disableCngCertificates, False)
```

<span data-ttu-id="e88f4-109">이러한 변경으로 인해 CNG 인증서와의 보안 통신을 시작하려는 시도에 종속되는 예외 처리 코드를 더 이상 실행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e88f4-109">Note that, because of this change, any exception handling code that depends on the attempt to initiate secure communication with a CNG certificate to fail will no longer execute.</span></span>

| <span data-ttu-id="e88f4-110">이름</span><span class="sxs-lookup"><span data-stu-id="e88f4-110">Name</span></span>    | <span data-ttu-id="e88f4-111">값</span><span class="sxs-lookup"><span data-stu-id="e88f4-111">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="e88f4-112">Scope</span><span class="sxs-lookup"><span data-stu-id="e88f4-112">Scope</span></span>   | <span data-ttu-id="e88f4-113">부</span><span class="sxs-lookup"><span data-stu-id="e88f4-113">Minor</span></span>       |
| <span data-ttu-id="e88f4-114">버전</span><span class="sxs-lookup"><span data-stu-id="e88f4-114">Version</span></span> | <span data-ttu-id="e88f4-115">4.6.2</span><span class="sxs-lookup"><span data-stu-id="e88f4-115">4.6.2</span></span>       |
| <span data-ttu-id="e88f4-116">형식</span><span class="sxs-lookup"><span data-stu-id="e88f4-116">Type</span></span>    | <span data-ttu-id="e88f4-117">대상 변경</span><span class="sxs-lookup"><span data-stu-id="e88f4-117">Retargeting</span></span> |
