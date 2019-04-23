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
ms.openlocfilehash: a89b29cd459060c93d5ca77bb2154e1a10b02d03
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59213652"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="a38a1-102">CreateIDispatchSTAForwarder 함수 (F 관리 되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="a38a1-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="a38a1-103">이 API는 Windows Presentation Foundation (WPF) 인프라를 지원 하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a38a1-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="a38a1-104">스레드 및 windows 관리에 대 한 Windows Presentation Foundation (WPF) 인프라에서 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="a38a1-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a38a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="a38a1-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,   
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="a38a1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a38a1-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="a38a1-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="a38a1-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="a38a1-108">pDispatchDelegate</span><span class="sxs-lookup"><span data-stu-id="a38a1-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="a38a1-109">에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a38a1-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="a38a1-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="a38a1-110">ppForwarder</span></span>  
 <span data-ttu-id="a38a1-111">주소에 대 한 포인터는 `IDispatch` 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="a38a1-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a38a1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a38a1-112">Requirements</span></span>  
 <span data-ttu-id="a38a1-113">**플랫폼:** 참조 [.NET Framework 시스템 요구 사항](../../get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="a38a1-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a38a1-114">**DLL:**</span><span class="sxs-lookup"><span data-stu-id="a38a1-114">**DLL:**</span></span>  
  
 <span data-ttu-id="a38a1-115">.NET framework 3.0 및 3.5. PresentationHostDLL.dll</span><span class="sxs-lookup"><span data-stu-id="a38a1-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="a38a1-116">.NET framework 4 이상: PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="a38a1-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="a38a1-117">**.NET framework 버전:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a38a1-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a38a1-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="a38a1-118">See also</span></span>

- [<span data-ttu-id="a38a1-119">F 관리되지 않는 API 참조</span><span class="sxs-lookup"><span data-stu-id="a38a1-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
