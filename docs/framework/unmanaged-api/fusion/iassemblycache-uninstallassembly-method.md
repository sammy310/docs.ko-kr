---
description: '자세한 정보: IAssemblyCache:: UninstallAssembly 메서드'
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
ms.openlocfilehash: d50108b9090b4250e8a6cec1d9b5c54bb78dee9c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760903"
---
# <a name="iassemblycacheuninstallassembly-method"></a><span data-ttu-id="69c07-103">IAssemblyCache::UninstallAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="69c07-103">IAssemblyCache::UninstallAssembly Method</span></span>

<span data-ttu-id="69c07-104">전역 어셈블리 캐시에서 지정 된 어셈블리를 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="69c07-104">Uninstalls the specified assembly from the global assembly cache.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="69c07-105">구문</span><span class="sxs-lookup"><span data-stu-id="69c07-105">Syntax</span></span>  
  
```cpp  
HRESULT UninstallAssembly (  
    [in] DWORD dwFlags,  
    [in] LPCWSTR pszAssemblyName,  
    [in] LPCFUSION_INSTALL_REFERENCE pRefData,  
    [out, optional] ULONG *pulDisposition  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="69c07-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="69c07-106">Parameters</span></span>  

 `dwFlags`  
 <span data-ttu-id="69c07-107">진행 Fusion에 정의 된 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="69c07-107">[in] Flags defined in Fusion.idl.</span></span>  
  
 `pszAssemblyName`  
 <span data-ttu-id="69c07-108">진행 제거할 어셈블리의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="69c07-108">[in] The name of the assembly to uninstall.</span></span>  
  
 `pRefData`  
 <span data-ttu-id="69c07-109">진행 어셈블리의 설치 데이터를 포함 하는 [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) 구조체입니다.</span><span class="sxs-lookup"><span data-stu-id="69c07-109">[in] A [FUSION_INSTALL_REFERENCE](fusion-install-reference-structure.md) structure that contains the installation data for the assembly.</span></span>  
  
 `pulDisposition`  
 <span data-ttu-id="69c07-110">[out, 선택 사항] Fusion에 정의 된 처리 값 중 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="69c07-110">[out, optional] One of the disposition values defined in Fusion.idl.</span></span> <span data-ttu-id="69c07-111">가능한 값은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="69c07-111">Possible values include the following:</span></span>  
  
- <span data-ttu-id="69c07-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span><span class="sxs-lookup"><span data-stu-id="69c07-112">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_UNINSTALLED (1)</span></span>  
  
- <span data-ttu-id="69c07-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span><span class="sxs-lookup"><span data-stu-id="69c07-113">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_STILL_IN_USE (2)</span></span>  
  
- <span data-ttu-id="69c07-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span><span class="sxs-lookup"><span data-stu-id="69c07-114">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_ALREADY_UNINSTALLED (3)</span></span>  
  
- <span data-ttu-id="69c07-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span><span class="sxs-lookup"><span data-stu-id="69c07-115">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_DELETE_PENDING (4)</span></span>  
  
- <span data-ttu-id="69c07-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span><span class="sxs-lookup"><span data-stu-id="69c07-116">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_HAS_INSTALL_REFERENCES (5)</span></span>  
  
- <span data-ttu-id="69c07-117">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span><span class="sxs-lookup"><span data-stu-id="69c07-117">IASSEMBLYCACHE_UNINSTALL_DISPOSITION_REFERENCE_NOT_FOUND (6)</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="69c07-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="69c07-118">Requirements</span></span>  

 <span data-ttu-id="69c07-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="69c07-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="69c07-120">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="69c07-120">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="69c07-121">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="69c07-121">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="69c07-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="69c07-122">See also</span></span>

- [<span data-ttu-id="69c07-123">IAssemblyCache 인터페이스</span><span class="sxs-lookup"><span data-stu-id="69c07-123">IAssemblyCache Interface</span></span>](iassemblycache-interface.md)
