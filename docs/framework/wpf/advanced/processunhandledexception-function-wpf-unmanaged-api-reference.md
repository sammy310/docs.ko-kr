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
ms.openlocfilehash: c3997415c19483a69e66d8fe68c6ec9241f7ad0d
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57356226"
---
# <a name="processunhandledexception-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="f442d-102">ProcessUnhandledException 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="f442d-102">ProcessUnhandledException Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="f442d-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f442d-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="f442d-104">예외 처리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f442d-104">Used by the Windows Presentation Foundation (WPF) infrastructure for exception handling.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f442d-105">구문</span><span class="sxs-lookup"><span data-stu-id="f442d-105">Syntax</span></span>  
  
```cpp  
void __stdcall ProcessUnhandledException(  
   __in_ecount(1) BSTR errorMsg  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="f442d-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f442d-106">Parameters</span></span>  
 <span data-ttu-id="f442d-107">errorMsg</span><span class="sxs-lookup"><span data-stu-id="f442d-107">errorMsg</span></span>  
 <span data-ttu-id="f442d-108">오류 메시지입니다.</span><span class="sxs-lookup"><span data-stu-id="f442d-108">The error message.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f442d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f442d-109">Requirements</span></span>  
 <span data-ttu-id="f442d-110">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f442d-110">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f442d-111">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="f442d-111">**DLL:**</span></span>  
  
 <span data-ttu-id="f442d-112">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="f442d-112">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="f442d-113">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="f442d-113">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="f442d-114">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f442d-114">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f442d-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="f442d-115">See also</span></span>
- [<span data-ttu-id="f442d-116">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="f442d-116">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
