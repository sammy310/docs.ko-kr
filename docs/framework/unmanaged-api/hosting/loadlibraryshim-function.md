---
title: LoadLibraryShim 함수
ms.date: 03/30/2017
api_name:
- LoadLibraryShim
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- LoadLibraryShim
helpviewer_keywords:
- LoadLibraryShim function [.NET Framework hosting]
ms.assetid: 30931874-4d0e-4df1-b3d1-e425b50655d1
topic_type:
- apiref
ms.openlocfilehash: 11bb220068e978dc130701e3b28ab3f421be7337
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/14/2020
ms.locfileid: "75937646"
---
# <a name="loadlibraryshim-function"></a><span data-ttu-id="1313a-102">LoadLibraryShim 함수</span><span class="sxs-lookup"><span data-stu-id="1313a-102">LoadLibraryShim Function</span></span>
<span data-ttu-id="1313a-103">.NET Framework 재배포 가능 패키지에 포함 된 DLL의 지정 된 버전을 로드 합니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-103">Loads a specified version of a DLL that is included in the .NET Framework redistributable package.</span></span>  
  
 <span data-ttu-id="1313a-104">이 함수는 .NET Framework 4에서 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-104">This function has been deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="1313a-105">대신 [ICLRRuntimeInfo:: LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) 메서드를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-105">Use the [ICLRRuntimeInfo::LoadLibrary](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-loadlibrary-method.md) method instead.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1313a-106">구문</span><span class="sxs-lookup"><span data-stu-id="1313a-106">Syntax</span></span>  
  
```cpp  
HRESULT LoadLibraryShim (  
    [in]  LPCWSTR  szDllName,  
    [in]  LPCWSTR  szVersion,  
          LPVOID   pvReserved,  
    [out] HMODULE *phModDll  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1313a-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1313a-107">Parameters</span></span>  
 `szDllName`  
 <span data-ttu-id="1313a-108">진행 .NET Framework 라이브러리에서 로드할 DLL의 이름을 나타내는 0으로 끝나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-108">[in] A zero-terminated string that represents the name of the DLL to be loaded from the .NET Framework library.</span></span>  
  
 `szVersion`  
 <span data-ttu-id="1313a-109">진행 로드할 DLL의 버전을 나타내는 0으로 끝나는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-109">[in] A zero-terminated string that represents the version of the DLL to be loaded.</span></span> <span data-ttu-id="1313a-110">`szVersion`가 null 이면 로드 하도록 선택한 버전이 버전 4 보다 작은 최신 버전의 지정 된 DLL입니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-110">If `szVersion` is null, the version selected for loading is the latest version of the specified DLL that is less than version 4.</span></span> <span data-ttu-id="1313a-111">즉, `szVersion`가 null 이면 버전 4 보다 크거나 같은 모든 버전이 무시 되 고 버전 4 보다 버전이 설치 되어 있지 않은 경우 DLL이 로드 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-111">That is, all versions equal to or greater than version 4 are ignored if `szVersion` is null, and if no version less than version 4 is installed, the DLL fails to load.</span></span> <span data-ttu-id="1313a-112">이는 .NET Framework 4 설치가 기존 응용 프로그램 또는 구성 요소에 영향을 주지 않도록 하기 위한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-112">This is to ensure that installation of the .NET Framework 4 does not affect pre-existing applications or components.</span></span> <span data-ttu-id="1313a-113">CLR 팀 블로그에서 [-Proc SxS 및 Migration 빠른 시작](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) 항목을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1313a-113">See the entry [In-Proc SxS and Migration Quick Start](https://devblogs.microsoft.com/dotnet/in-proc-sxs-and-migration-quick-start/) in the CLR team blog.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="1313a-114">나중에 사용하기 위해 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-114">Reserved for future use.</span></span>  
  
 `phModDll`  
 <span data-ttu-id="1313a-115">제한이 모듈의 핸들에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-115">[out] A pointer to the handle of the module.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1313a-116">반환 값</span><span class="sxs-lookup"><span data-stu-id="1313a-116">Return Value</span></span>  
 <span data-ttu-id="1313a-117">이 메서드는 Winerror.h에 정의 된 대로 다음 값 외에 표준 COM (구성 요소 개체 모델) 오류 코드를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-117">This method returns standard Component Object Model (COM) error codes, as defined in WinError.h, in addition to the following values.</span></span>  
  
|<span data-ttu-id="1313a-118">반환 코드</span><span class="sxs-lookup"><span data-stu-id="1313a-118">Return code</span></span>|<span data-ttu-id="1313a-119">설명</span><span class="sxs-lookup"><span data-stu-id="1313a-119">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="1313a-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="1313a-120">S_OK</span></span>|<span data-ttu-id="1313a-121">메서드가 성공적으로 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="1313a-122">CLR_E_SHIM_RUNTIMELOAD</span><span class="sxs-lookup"><span data-stu-id="1313a-122">CLR_E_SHIM_RUNTIMELOAD</span></span>|<span data-ttu-id="1313a-123">`szDllName`를 로드 하려면 CLR (공용 언어 런타임)을 로드 해야 하며 CLR의 필수 버전을 로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-123">Loading `szDllName` requires loading the common language runtime (CLR), and the necessary version of the CLR cannot be loaded.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="1313a-124">주의</span><span class="sxs-lookup"><span data-stu-id="1313a-124">Remarks</span></span>  
 <span data-ttu-id="1313a-125">이 함수는 .NET Framework 재배포 가능 패키지에 포함 된 Dll을 로드 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-125">This function is used to load DLLs that are included in the .NET Framework redistributable package.</span></span> <span data-ttu-id="1313a-126">사용자가 생성 한 Dll은 로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-126">It does not load user-generated DLLs.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="1313a-127">.NET Framework 버전 2.0부터 Fusion .dll을 로드 하면 CLR이 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-127">Beginning with the .NET Framework version 2.0, loading Fusion.dll causes the CLR to be loaded.</span></span> <span data-ttu-id="1313a-128">이는 Fusion의 함수는 이제 런타임이 제공 하는 구현이 있는 래퍼 이기 때문입니다.</span><span class="sxs-lookup"><span data-stu-id="1313a-128">This is because the functions in Fusion.dll are now wrappers whose implementations are provided by the runtime.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1313a-129">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1313a-129">Requirements</span></span>  
 <span data-ttu-id="1313a-130">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1313a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1313a-131">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1313a-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="1313a-132">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1313a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1313a-133">참조</span><span class="sxs-lookup"><span data-stu-id="1313a-133">See also</span></span>

- [<span data-ttu-id="1313a-134">사용되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="1313a-134">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
