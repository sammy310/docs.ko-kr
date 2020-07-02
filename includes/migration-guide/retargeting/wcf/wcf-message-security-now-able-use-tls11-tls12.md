---
ms.openlocfilehash: c646372104457e8bc5d418744847f3ee771c8d8b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/01/2020
ms.locfileid: "85614806"
---
### <a name="wcf-message-security-now-is-able-to-use-tls11-and-tls12"></a><span data-ttu-id="cd999-101">WCF 메시지 보안이 이제 TLS1.1 및 TLS1.2를 사용할 수 있음</span><span class="sxs-lookup"><span data-stu-id="cd999-101">WCF message security now is able to use TLS1.1 and TLS1.2</span></span>

#### <a name="details"></a><span data-ttu-id="cd999-102">설명</span><span class="sxs-lookup"><span data-stu-id="cd999-102">Details</span></span>

<span data-ttu-id="cd999-103">.NET Framework 4.7부터 고객은 애플리케이션 구성 설정을 통해 SSL3.0 및 TLS1.0 외에도 WCF 메시지 보안에 TLS1.1 또는 TLS1.2를 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd999-103">Starting in the .NET Framework 4.7, customers can configure either TLS1.1 or TLS1.2 in WCF message security in addition to SSL3.0 and TLS1.0 through application configuration settings.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="cd999-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="cd999-104">Suggestion</span></span>

<span data-ttu-id="cd999-105">.NET Framework 4.7에서는 WCF 메시지 보안의 TLS1.1 및 TLS1.2에 대한 지원은 기본적으로 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cd999-105">In the .NET Framework 4.7, support for TLS1.1 and TLS1.2 in WCF message security is disabled by default.</span></span> <span data-ttu-id="cd999-106">app.config 또는 web.config 파일의 `<runtime>` 섹션에 다음 행을 추가하여 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd999-106">You can enable it by adding the following line to the `<runtime>` section of the app.config or web.config file:</span></span>

```xml
<runtime>
<AppContextSwitchOverrides value="Switch.System.ServiceModel.DisableUsingServicePointManagerSecurityProtocols=false;Switch.System.Net.DontEnableSchUseStrongCrypto=false" />
</runtime>
```

| <span data-ttu-id="cd999-107">이름</span><span class="sxs-lookup"><span data-stu-id="cd999-107">Name</span></span>    | <span data-ttu-id="cd999-108">값</span><span class="sxs-lookup"><span data-stu-id="cd999-108">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="cd999-109">Scope</span><span class="sxs-lookup"><span data-stu-id="cd999-109">Scope</span></span>   | <span data-ttu-id="cd999-110">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cd999-110">Edge</span></span>        |
| <span data-ttu-id="cd999-111">버전</span><span class="sxs-lookup"><span data-stu-id="cd999-111">Version</span></span> | <span data-ttu-id="cd999-112">4.7</span><span class="sxs-lookup"><span data-stu-id="cd999-112">4.7</span></span>         |
| <span data-ttu-id="cd999-113">형식</span><span class="sxs-lookup"><span data-stu-id="cd999-113">Type</span></span>    | <span data-ttu-id="cd999-114">대상 변경</span><span class="sxs-lookup"><span data-stu-id="cd999-114">Retargeting</span></span> |
