---
title: IAssemblyCache::UninstallAssembly 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyCache.UninstallAssembly
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCache::UninstallAssembly
helpviewer_keywords:
- UninstallAssembly method [.NET Framework fusion]
- IAssemblyCache::UninstallAssembly method [.NET Framework fusion]
ms.assetid: 973b2c44-8dfc-40c1-9035-10f4846627e9
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 75ef24162adbb653671ed070587e7155fae6b949
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697747"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="463fe-102">IAssemblyCache::UninstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="463fe-102">IAssemblyCache::UninstallAssembly Method</span></span>
<span data-ttu-id="463fe-103">전역 어셈블리 캐시에서 지정된 된 어셈블리를 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="463fe-103">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="463fe-104">구문</span><span class="sxs-lookup"><span data-stu-id="463fe-104">Syntax</span></span>  
  
```  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="463fe-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="463fe-105">Parameters</span></span>  
 `dwFlags`  
 <span data-ttu-id="463fe-106">[in] 같은 값이 지원에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="463fe-106">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="463fe-107">[in] 제거할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="463fe-107">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="463fe-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) 어셈블리에 대해 설치 데이터가 포함 된 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="463fe-108">[in] A [FUSION_INSTALL_REFERENCE](../../../../docs/framework/unmanaged-api/fusion/fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="463fe-109">[out, optional] 같은 값이 지원에 정의 된 처리 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="463fe-109">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="463fe-110">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="463fe-110">Possible values include the following:</span></span>  
  
- <span data-ttu-id="463fe-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="463fe-111">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="463fe-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="463fe-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="463fe-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="463fe-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="463fe-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="463fe-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="463fe-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="463fe-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="463fe-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="463fe-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="463fe-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="463fe-117">Requirements</span></span>  
 <span data-ttu-id="463fe-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="463fe-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="463fe-119">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="463fe-119">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="463fe-120">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="463fe-120">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="463fe-121">참고자료</span><span class="sxs-lookup"><span data-stu-id="463fe-121">See also</span></span>

- [<span data-ttu-id="463fe-122">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="463fe-122">IAssemblyCache Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
