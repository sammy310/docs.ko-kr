---
title: LoadFromHistory 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- LoadFromHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: d037c062-a911-4949-b251-ccd3e48b1d17
ms.openlocfilehash: 7807e073d1f09ac6a6213aee6d86d53cc75a3c56
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76727932"
---
# <a name="loadfromhistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="ef645-102">LoadFromHistory 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="ef645-102">LoadFromHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="ef645-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="ef645-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="ef645-104">Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ef645-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ef645-105">구문</span><span class="sxs-lookup"><span data-stu-id="ef645-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadFromHistory_export(  
        IStream* pHistoryStream,   
        IBindCtx* pBindCtx  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="ef645-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ef645-106">Parameters</span></span>  
 <span data-ttu-id="ef645-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="ef645-107">pHistoryStream</span></span>  
 <span data-ttu-id="ef645-108">기록 정보 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef645-108">A pointer to a stream of history information.</span></span>  
  
 <span data-ttu-id="ef645-109">pBindCtx</span><span class="sxs-lookup"><span data-stu-id="ef645-109">pBindCtx</span></span>  
 <span data-ttu-id="ef645-110">바인드 컨텍스트에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ef645-110">A pointer to a bind context.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef645-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ef645-111">Requirements</span></span>  
 <span data-ttu-id="ef645-112">**플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="ef645-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef645-113">**GDIPLUS.DLL**</span><span class="sxs-lookup"><span data-stu-id="ef645-113">**DLL:**</span></span>  
  
 <span data-ttu-id="ef645-114">.NET Framework 3.0 및 3.5: PresentationHostDLL에서</span><span class="sxs-lookup"><span data-stu-id="ef645-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="ef645-115">.NET Framework 4 이상: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="ef645-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="ef645-116">**.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef645-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef645-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ef645-117">See also</span></span>

- [<span data-ttu-id="ef645-118">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="ef645-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
