---
ms.openlocfilehash: b4e062fe3a00b76da144e706841f87b2a95888e5
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59774412"
---
### <a name="encoderparameter-ctor-is-obsolete"></a><span data-ttu-id="d776f-101">EncoderParameter ctor가 사용되지 않음</span><span class="sxs-lookup"><span data-stu-id="d776f-101">EncoderParameter ctor is obsolete</span></span>

|   |   |
|---|---|
|<span data-ttu-id="d776f-102">세부 정보</span><span class="sxs-lookup"><span data-stu-id="d776f-102">Details</span></span>|<span data-ttu-id="d776f-103"><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> 생성자는 이제 사용되지 않으며 사용하는 경우 빌드 경고가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d776f-103">The <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> constructor is obsolete now and will introduce build warnings if used.</span></span>|
|<span data-ttu-id="d776f-104">제안 해결 방법</span><span class="sxs-lookup"><span data-stu-id="d776f-104">Suggestion</span></span>|<span data-ttu-id="d776f-105"><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)> 생성자가 계속 작동하지만 .NET Framework 4.5 도구를 사용하여 코드를 다시 컴파일할 때 사용되지 않는 빌드 경고를 방지하려면 다음 생성자를 대신 사용해야 합니다<xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span><span class="sxs-lookup"><span data-stu-id="d776f-105">Although the <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)>constructor will continue to work, the following constructor should be used instead to avoid the obsolete build warning when re-compiling code with .NET Framework  4.5 tools: <xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Drawing.Imaging.EncoderParameterValueType,System.IntPtr)>.</span></span>|
|<span data-ttu-id="d776f-106">범위</span><span class="sxs-lookup"><span data-stu-id="d776f-106">Scope</span></span>|<span data-ttu-id="d776f-107">부</span><span class="sxs-lookup"><span data-stu-id="d776f-107">Minor</span></span>|
|<span data-ttu-id="d776f-108">버전</span><span class="sxs-lookup"><span data-stu-id="d776f-108">Version</span></span>|<span data-ttu-id="d776f-109">4.5</span><span class="sxs-lookup"><span data-stu-id="d776f-109">4.5</span></span>|
|<span data-ttu-id="d776f-110">형식</span><span class="sxs-lookup"><span data-stu-id="d776f-110">Type</span></span>|<span data-ttu-id="d776f-111">대상 변경</span><span class="sxs-lookup"><span data-stu-id="d776f-111">Retargeting</span></span>|
|<span data-ttu-id="d776f-112">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="d776f-112">Affected APIs</span></span>|<ul><li><xref:System.Drawing.Imaging.EncoderParameter.%23ctor(System.Drawing.Imaging.Encoder,System.Int32,System.Int32,System.Int32,System.Int32)?displayProperty=nameWithType></li></ul>|
