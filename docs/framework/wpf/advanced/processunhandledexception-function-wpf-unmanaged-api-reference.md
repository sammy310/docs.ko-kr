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
ms.openlocfilehash: 0c8751454be6e0eed547c38e9d0bc7931abaec3d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59196972"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="12236-102">ProcessUnhandledException 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="12236-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="12236-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="12236-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="12236-104">예외 처리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="12236-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="12236-105">구문</span><span class="sxs-lookup"><span data-stu-id="12236-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="12236-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="12236-106">Parameters</span></span>  
 <span data-ttu-id="12236-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="12236-107">errorMsg</span></span>  
 <span data-ttu-id="12236-108">오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="12236-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="12236-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="12236-109">Requirements</span></span>  
 <span data-ttu-id="12236-110">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="12236-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="12236-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="12236-111">**DLL:**</span></span>  
  
 <span data-ttu-id="12236-112">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="12236-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="12236-113">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="12236-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="12236-114">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="12236-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12236-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="12236-115">See also</span></span>

- [<span data-ttu-id="12236-116">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="12236-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
