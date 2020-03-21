---
title: 로드로부터 역사 함수 - WPF 관리되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: be9b8658614e678b4370044a753554859d230fed
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79141577"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="b4e6f-102">로드로부터 역사 함수 (WPF 관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="b4e6f-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="b4e6f-103">이 API는 WPF(Windows 프레젠테이션 기반) 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b4e6f-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="b4e6f-104">Windows 관리를 위한 WPF(Windows 프레젠테이션 재단) 인프라에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="b4e6f-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4e6f-105">구문</span><span class="sxs-lookup"><span data-stu-id="b4e6f-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="b4e6f-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4e6f-106">Parameters</span></span>  
 <span data-ttu-id="b4e6f-107">p히스토리스트림</span><span class="sxs-lookup"><span data-stu-id="b4e6f-107">pHistoryStream</span></span>  
 <span data-ttu-id="b4e6f-108">기록 정보 스트림에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e6f-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="b4e6f-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="b4e6f-109">pBindCtx</span></span>  
 <span data-ttu-id="b4e6f-110">바인딩 컨텍스트에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4e6f-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b4e6f-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4e6f-111">Requirements</span></span>  
 <span data-ttu-id="b4e6f-112">**플랫폼:** [.NET 프레임워크 시스템 요구 사항을 참조하십시오.](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="b4e6f-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4e6f-113">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="b4e6f-113">**DLL:**</span></span>  
  
 <span data-ttu-id="b4e6f-114">.NET 프레임워크 3.0 및 3.5: 프레젠테이션호스트DLL.dll</span><span class="sxs-lookup"><span data-stu-id="b4e6f-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="b4e6f-115">.NET 프레임워크 4 이상에서 PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="b4e6f-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="b4e6f-116">**.NET 프레임워크 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4e6f-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4e6f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4e6f-117">See also</span></span>

- [<span data-ttu-id="b4e6f-118">WPF 비관리형 API 참조</span><span class="sxs-lookup"><span data-stu-id="b4e6f-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
