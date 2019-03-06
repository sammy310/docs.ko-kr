---
title: CreateIDispatchSTAForwarder 함수 (F 관리 되지 않는 API 참조)
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: c4da322bf779e084f12529d0da6949ef6ada5cf3
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2019
ms.locfileid: "57379655"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="381c8-102">CreateIDispatchSTAForwarder 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="381c8-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="381c8-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="381c8-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="381c8-104">스레드 및 windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="381c8-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="381c8-105">구문</span><span class="sxs-lookup"><span data-stu-id="381c8-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="381c8-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="381c8-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="381c8-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="381c8-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="381c8-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="381c8-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="381c8-109">에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="381c8-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="381c8-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="381c8-110">ppForwarder</span></span>  
 <span data-ttu-id="381c8-111">주소에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="381c8-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="381c8-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="381c8-112">Requirements</span></span>  
 <span data-ttu-id="381c8-113">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="381c8-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="381c8-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="381c8-114">**DLL:**</span></span>  
  
 <span data-ttu-id="381c8-115">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="381c8-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="381c8-116">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="381c8-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="381c8-117">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="381c8-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="381c8-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="381c8-118">See also</span></span>
- [<span data-ttu-id="381c8-119">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="381c8-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
