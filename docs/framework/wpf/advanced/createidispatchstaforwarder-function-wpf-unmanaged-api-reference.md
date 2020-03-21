---
title: 만들기IDispatchSTA포워더 기능 - WPF 관리되지 않는 API 참조
titleSuffix: ''
ms.date: 03/30/2017
dev_langs:
- cpp
api_name:
- CreateIDispatchSTAForwarder
api_location:
- PresentationHost_v0400.dll
ms.assetid: 57a02dfa-f091-4ace-9c06-1f4ab52b3527
ms.openlocfilehash: e151ffa6eb5f1dc7479c699e0d7f9f3f57833ebd
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174721"
---
# <a name="createidispatchstaforwarder-function-wpf-unmanaged-api-reference"></a><span data-ttu-id="da2cb-102">생성IDispatchSTA포이퍼 함수(WPF 관리되지 않는 API 참조)</span><span class="sxs-lookup"><span data-stu-id="da2cb-102">CreateIDispatchSTAForwarder Function (WPF Unmanaged API Reference)</span></span>
<span data-ttu-id="da2cb-103">이 API는 WPF(Windows 프레젠테이션 기반) 인프라를 지원하며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-103">This API supports the Windows Presentation Foundation (WPF) infrastructure and is not intended to be used directly from your code.</span></span>  
  
 <span data-ttu-id="da2cb-104">스레드 및 창 관리를 위해 WPF(Windows 프레젠테이션 재단) 인프라에서 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-104">Used by the Windows Presentation Foundation (WPF) infrastructure for thread and windows management.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="da2cb-105">구문</span><span class="sxs-lookup"><span data-stu-id="da2cb-105">Syntax</span></span>  
  
```cpp  
HRESULT CreateIDispatchSTAForwarder(  
   __in IDispatch *pDispatchDelegate,
   __deref_out IDispatch **ppForwarder  
)  
```  
  
## <a name="parameters"></a><span data-ttu-id="da2cb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="da2cb-106">Parameters</span></span>  
  
## <a name="property-valuereturn-value"></a><span data-ttu-id="da2cb-107">속성 값/반환 값</span><span class="sxs-lookup"><span data-stu-id="da2cb-107">Property Value/Return Value</span></span>  
 <span data-ttu-id="da2cb-108">p디스패치대리자</span><span class="sxs-lookup"><span data-stu-id="da2cb-108">pDispatchDelegate</span></span>  
 <span data-ttu-id="da2cb-109">인터페이스에 대한 `IDispatch` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-109">A pointer to an `IDispatch` interface.</span></span>  
  
 <span data-ttu-id="da2cb-110">ppForwarder</span><span class="sxs-lookup"><span data-stu-id="da2cb-110">ppForwarder</span></span>  
 <span data-ttu-id="da2cb-111">인터페이스의 주소에 대한 `IDispatch` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="da2cb-111">A pointer to the address of an `IDispatch` interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="da2cb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="da2cb-112">Requirements</span></span>  
 <span data-ttu-id="da2cb-113">**플랫폼:** [.NET 프레임워크 시스템 요구 사항을 참조하십시오.](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="da2cb-113">**Platforms:** See [.NET Framework System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da2cb-114">**Dll:**</span><span class="sxs-lookup"><span data-stu-id="da2cb-114">**DLL:**</span></span>  
  
 <span data-ttu-id="da2cb-115">.NET 프레임워크 3.0 및 3.5: 프레젠테이션호스트DLL.dll</span><span class="sxs-lookup"><span data-stu-id="da2cb-115">In the .NET Framework 3.0 and 3.5: PresentationHostDLL.dll</span></span>  
  
 <span data-ttu-id="da2cb-116">.NET 프레임워크 4 이상에서 PresentationHost_v0400.dll</span><span class="sxs-lookup"><span data-stu-id="da2cb-116">In the .NET Framework 4 and later: PresentationHost_v0400.dll</span></span>  
  
 <span data-ttu-id="da2cb-117">**.NET 프레임워크 버전:**[!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="da2cb-117">**.NET Framework Version:** [!INCLUDE[net_current_v30plus](../../../../includes/net-current-v30plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da2cb-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="da2cb-118">See also</span></span>

- [<span data-ttu-id="da2cb-119">WPF 비관리형 API 참조</span><span class="sxs-lookup"><span data-stu-id="da2cb-119">WPF Unmanaged API Reference</span></span>](wpf-unmanaged-api-reference.md)
