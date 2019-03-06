---
title: ProcessUnhandledException 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- ProcessUnhandledException
api_location:
- PresentationHost_v0400.dll
ms.assetid: 495ce5f6-bb4d-4b30-807a-c3c35f1ca95c
ms.openlocfilehash: 3a95e8e68361f060d843247f400043a79dc28889
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57466867"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="36ca0-102">ProcessUnhandledException 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="36ca0-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="36ca0-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="36ca0-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="36ca0-104">예외 처리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="36ca0-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="36ca0-105">구문</span><span class="sxs-lookup"><span data-stu-id="36ca0-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="36ca0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="36ca0-106">Parameters</span></span>  
 <span data-ttu-id="36ca0-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="36ca0-107">errorMsg</span></span>  
 <span data-ttu-id="36ca0-108">오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="36ca0-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="36ca0-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="36ca0-109">Requirements</span></span>  
 <span data-ttu-id="36ca0-110">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="36ca0-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="36ca0-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="36ca0-111">**DLL:**</span></span>  
  
 <span data-ttu-id="36ca0-112">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="36ca0-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="36ca0-113">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="36ca0-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="36ca0-114">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="36ca0-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="36ca0-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="36ca0-115">See also</span></span>
- [<span data-ttu-id="36ca0-116">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="36ca0-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
