---
title: CreateIDispatchSTAForwarder 함수-WPF 관리 되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: 67f2542733fb9c6af197c99ede2bd097ce876b5d
ms.sourcegitcommit: de17a7a0a37042f0d4406f5ae5393531caeb25ba
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2020
ms.locfileid: "76738033"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="c93c2-102">CreateIDispatchSTAForwarder 함수 (WPF 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="c93c2-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="c93c2-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 사용자 코드에서 직접 사용 하기 위한 것이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="c93c2-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="c93c2-104">스레드 및 Windows 관리를 위한 WPF (Windows Presentation Foundation) 인프라에서 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c93c2-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c93c2-105">구문</span><span class="sxs-lookup"><span data-stu-id="c93c2-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="c93c2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c93c2-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="c93c2-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="c93c2-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="c93c2-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="c93c2-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="c93c2-109">`IDispatch` 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c93c2-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="c93c2-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="c93c2-110">ppForwarder</span></span>  
 <span data-ttu-id="c93c2-111">`IDispatch` 인터페이스의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c93c2-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c93c2-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c93c2-112">Requirements</span></span>  
 <span data-ttu-id="c93c2-113">**플랫폼:** [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c93c2-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c93c2-114">**GDIPLUS.DLL**</span><span class="sxs-lookup"><span data-stu-id="c93c2-114">**DLL:**</span></span>  
  
 <span data-ttu-id="c93c2-115">.NET Framework 3.0 및 3.5: PresentationHostDLL에서</span><span class="sxs-lookup"><span data-stu-id="c93c2-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="c93c2-116">.NET Framework 4 이상: PresentationHost_v0400 .dll</span><span class="sxs-lookup"><span data-stu-id="c93c2-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="c93c2-117">**.NET Framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c93c2-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c93c2-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c93c2-118">See also</span></span>

- [<span data-ttu-id="c93c2-119">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="c93c2-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
