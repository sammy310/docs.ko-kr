---
title: 포워드번역가속기 함수 - WPF 관리되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ForwardTranslateAccelerator
api_location:
- PresentationHost_v0400.dll
ms.assetid: fff47a86-9d9f-4176-9530-10e1876e393f
ms.openlocfilehash: a0a01be3000dc53df7855cb74015ba1164206838
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186627"
---
# <a name="forwardtranslateaccelerator-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="16416-102">포워드번역가속기 함수(WPF 비관리 API 참조)</span><span class="sxs-lookup"><span data-stu-id="16416-102">ForwardTranslateAccelerator Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="16416-103">이 API는 WPF(Windows 프레젠테이션 기반) 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="16416-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="16416-104">Windows 관리를 위한 WPF(Windows 프레젠테이션 재단) 인프라에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="16416-104">Used by the Windows Presentation Foundation (WPF) infrastructure for windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16416-105">구문</span><span class="sxs-lookup"><span data-stu-id="16416-105">Syntax</span></span>  
  
```cpp  
HRESULT ForwardTranslateAccelerator(  
   MSG* pMsg,
   VARIANT_BOOL appUnhandled  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="16416-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="16416-106">Parameters</span></span>  
 <span data-ttu-id="16416-107">pMsg</span><span class="sxs-lookup"><span data-stu-id="16416-107">pMsg</span></span>  
 <span data-ttu-id="16416-108">메시지에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="16416-108">A pointer to a message.</span></span>  
  
 <span data-ttu-id="16416-109">app처리되지 않음</span><span class="sxs-lookup"><span data-stu-id="16416-109">appUnhandled</span></span>  
 <span data-ttu-id="16416-110">`true`앱에 입력 메시지를 처리할 수 있는 기회가 이미 주어졌지만 처리하지 않은 경우 그렇지 `false`않으면 .</span><span class="sxs-lookup"><span data-stu-id="16416-110">`true` when the app has already been given a chance to handle the input message, but has not handled it; otherwise, `false`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="16416-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="16416-111">Requirements</span></span>  
 <span data-ttu-id="16416-112">**플랫폼:** [.NET 프레임워크 시스템 요구 사항을 참조하십시오.](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="16416-112">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16416-113">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="16416-113">**DLL:**</span></span>  
  
 <span data-ttu-id="16416-114">.NET 프레임워크 3.0 및 3.5: 프레젠테이션호스트DLL.dll</span><span class="sxs-lookup"><span data-stu-id="16416-114">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="16416-115">.NET 프레임워크 4 이상에서 PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="16416-115">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="16416-116">**.NET 프레임워크 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="16416-116">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16416-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="16416-117">See also</span></span>

- [<span data-ttu-id="16416-118">WPF 비관리형 API 참조</span><span class="sxs-lookup"><span data-stu-id="16416-118">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
