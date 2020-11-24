---
title: ICLRRuntimeInfo::LoadLibrary 메서드
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadLibrary
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadLibrary
helpviewer_keywords:
- ICLRRuntimeInfo::LoadLibrary method [.NET Framework hosting]
- LoadLibrary method [.NET Framework hosting]
ms.assetid: 4517ada3-4417-4ac5-a150-73da7a87c686
topic_type:
- apiref
ms.openlocfilehash: aa45c814568188a5fe93e3acd2514cb54bb0f984
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95688616"
---
# <a name="iclrruntimeinfoloadlibrary-method"></a><span data-ttu-id="5cc0c-102">ICLRRuntimeInfo::LoadLibrary 메서드</span><span class="sxs-lookup"><span data-stu-id="5cc0c-102">ICLRRuntimeInfo::LoadLibrary Method</span></span>

<span data-ttu-id="5cc0c-103">[ICLRRuntimeInfo](iclrruntimeinfo-interface.md) 인터페이스로 표시 되는 CLR (공용 언어 런타임)에서 .NET Framework 라이브러리를 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-103">Loads a .NET Framework library from the common language runtime (CLR) represented by an [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface.</span></span>  
  
 <span data-ttu-id="5cc0c-104">이 메서드는 [LoadLibraryShim](loadlibraryshim-function.md) 함수를 대체 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-104">This method supersedes the [LoadLibraryShim](loadlibraryshim-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5cc0c-105">구문</span><span class="sxs-lookup"><span data-stu-id="5cc0c-105">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibrary(  
     [in]  LPCWSTR pwzDllName,  
     [out, retval] HMODULE *phndModule);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5cc0c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5cc0c-106">Parameters</span></span>  

 `pwzDllName`  
 <span data-ttu-id="5cc0c-107">진행 로드할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-107">[in] The name of the assembly to be loaded.</span></span>  
  
 `phndModule`  
 <span data-ttu-id="5cc0c-108">제한이 로드 된 어셈블리에 대 한 핸들입니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-108">[out] A handle to the loaded assembly.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5cc0c-109">반환 값</span><span class="sxs-lookup"><span data-stu-id="5cc0c-109">Return Value</span></span>  

 <span data-ttu-id="5cc0c-110">이 메서드는 다음과 같은 특정 HRESULT뿐만 아니라 메서드 오류를 나타내는 HRESULT 오류도 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="5cc0c-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5cc0c-111">HRESULT</span></span>|<span data-ttu-id="5cc0c-112">설명</span><span class="sxs-lookup"><span data-stu-id="5cc0c-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5cc0c-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="5cc0c-113">S_OK</span></span>|<span data-ttu-id="5cc0c-114">메서드가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="5cc0c-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="5cc0c-115">E_POINTER</span></span>|<span data-ttu-id="5cc0c-116">`pwzDllName` 또는 `phndModule`가 null입니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-116">`pwzDllName` or `phndModule` is null.</span></span>|  
|<span data-ttu-id="5cc0c-117">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="5cc0c-117">E_OUTOFMEMORY</span></span>|<span data-ttu-id="5cc0c-118">메모리가 부족 하 여 요청을 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-118">Not enough memory is available to handle the request.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5cc0c-119">설명</span><span class="sxs-lookup"><span data-stu-id="5cc0c-119">Remarks</span></span>  

 <span data-ttu-id="5cc0c-120">이 메서드는 .NET Framework 재배포 가능 패키지에 포함 된 Dll만 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-120">This method only loads DLLs included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="5cc0c-121">사용자가 생성 한 어셈블리를 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-121">It can not load user-generated assemblies.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5cc0c-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5cc0c-122">Requirements</span></span>  

 <span data-ttu-id="5cc0c-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5cc0c-124">**헤더:** MetaHost</span><span class="sxs-lookup"><span data-stu-id="5cc0c-124">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="5cc0c-125">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5cc0c-125">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5cc0c-126">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5cc0c-126">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5cc0c-127">참조</span><span class="sxs-lookup"><span data-stu-id="5cc0c-127">See also</span></span>

- [<span data-ttu-id="5cc0c-128">ICLRRuntimeInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cc0c-128">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="5cc0c-129">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5cc0c-129">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="5cc0c-130">호스팅</span><span class="sxs-lookup"><span data-stu-id="5cc0c-130">Hosting</span></span>](index.md)
