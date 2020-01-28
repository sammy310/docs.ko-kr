---
title: ProcessUnhandledException 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 757e5ac3aa2dc4c87b210b026998523bd82045c1
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76743927"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="bc38a-102">ProcessUnhandledException 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="bc38a-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="bc38a-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="bc38a-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="bc38a-104">Windows Presentation Foundation (WPF) 인프라에서 예외 처리에 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc38a-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bc38a-105">구문</span><span class="sxs-lookup"><span data-stu-id="bc38a-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="bc38a-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bc38a-106">Parameters</span></span>  
 <span data-ttu-id="bc38a-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="bc38a-107">errorMsg</span></span>  
 <span data-ttu-id="bc38a-108">오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="bc38a-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bc38a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bc38a-109">Requirements</span></span>  
 <span data-ttu-id="bc38a-110">**플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bc38a-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bc38a-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="bc38a-111">**DLL:**</span></span>  
  
 <span data-ttu-id="bc38a-112">.NET Framework 3.0 및 3.5: PresentationHostDLL에서</span><span class="sxs-lookup"><span data-stu-id="bc38a-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="bc38a-113">.NET Framework 4 이상: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="bc38a-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="bc38a-114">**.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bc38a-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bc38a-115">참조</span><span class="sxs-lookup"><span data-stu-id="bc38a-115">See also</span></span>

- [<span data-ttu-id="bc38a-116">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="bc38a-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
