---
title: SaveToHistory 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- SaveToHistory
api_location:
- PresentationHost_v0400.dll
ms.assetid: 6dd101a3-44ad-4143-b228-772156f9b8ff
ms.openlocfilehash: 7337e5dc23a3dce5de8270902bce228c49bc6edb
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76731756"
---
# <a name="savetohistory-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="d29a8-102">SaveToHistory 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="d29a8-102">SaveToHistory Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="d29a8-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="d29a8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="d29a8-104">Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="d29a8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d29a8-105">구문</span><span class="sxs-lookup"><span data-stu-id="d29a8-105">Syntax</span></span>  
  
```cpp  
HRESULT SaveToHistory(  
   __in_ecount(1) IStream* pHistoryStream  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="d29a8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d29a8-106">Parameters</span></span>  
 <span data-ttu-id="d29a8-107">pHistoryStream</span><span class="sxs-lookup"><span data-stu-id="d29a8-107">pHistoryStream</span></span>  
 <span data-ttu-id="d29a8-108">기록 스트림에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="d29a8-108">A pointer to the history stream.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d29a8-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d29a8-109">Requirements</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d29a8-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d29a8-110">Requirements</span></span>  
 <span data-ttu-id="d29a8-111">**플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="d29a8-111">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d29a8-112">**GDIPLUS.DLL**</span><span class="sxs-lookup"><span data-stu-id="d29a8-112">**DLL:**</span></span>  
  
 <span data-ttu-id="d29a8-113">.NET Framework 3.0 및 3.5: PresentationHostDLL에서</span><span class="sxs-lookup"><span data-stu-id="d29a8-113">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="d29a8-114">.NET Framework 4 이상: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="d29a8-114">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="d29a8-115">**.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d29a8-115">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d29a8-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d29a8-116">See also</span></span>

- [<span data-ttu-id="d29a8-117">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="d29a8-117">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
