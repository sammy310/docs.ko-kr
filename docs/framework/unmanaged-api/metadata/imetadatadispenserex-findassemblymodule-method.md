---
title: IMetaDataDispenserEx::FindAssemblyModule 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.FindAssemblyModule
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::FindAssemblyModule
helpviewer_keywords:
- FindAssemblyModule method [.NET Framework metadata]
- IMetaDataDispenserEx::FindAssemblyModule method [.NET Framework metadata]
ms.assetid: d1fb65e1-7e19-4513-85b1-44f87c294d3e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ccb6331399ef3479e43bdb9dc4a72b5fd196672c
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495340"
---
# <a name="imetadatadispenserexfindassemblymodule-method"></a><span data-ttu-id="d06eb-102">IMetaDataDispenserEx::FindAssemblyModule 메서드</span><span class="sxs-lookup"><span data-stu-id="d06eb-102">IMetaDataDispenserEx::FindAssemblyModule Method</span></span>
<span data-ttu-id="d06eb-103">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-103">This method is not implemented.</span></span> <span data-ttu-id="d06eb-104">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d06eb-105">구문</span><span class="sxs-lookup"><span data-stu-id="d06eb-105">Syntax</span></span>  
  
```  
HRESULT FindAssemblyModule(  
    [in]  LPCWSTR  szAppBase,  
    [in]  LPCWSTR  szPrivateBin,  
    [in]  LPCWSTR  szGlobalBin,  
    [in]  LPCWSTR  szAssemblyName,  
    [in]  LPCWSTR  szModuleName,  
    [out] LPCWSTR  szName,  
    [in]  ULONG    cchName,  
    [out] ULONG    *pcName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d06eb-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d06eb-106">Parameters</span></span>  
 `szAppBase`  
 <span data-ttu-id="d06eb-107">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-107">[in] Not used.</span></span>  
  
 `szPrivateBin`  
 <span data-ttu-id="d06eb-108">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-108">[in] Not used.</span></span>  
  
 `szGlobalBin`  
 <span data-ttu-id="d06eb-109">[in] 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-109">[in] Not used.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="d06eb-110">[in] 모듈의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-110">[in] The name of the module.</span></span>  
  
 `szModuleName`  
 <span data-ttu-id="d06eb-111">[in] 어셈블리를 찾을 수입니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-111">[in] The assembly to be found.</span></span>  
  
 `szName`  
 <span data-ttu-id="d06eb-112">[out] 어셈블리의 단순한 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-112">[out] The simple name of the assembly.</span></span>  
  
 `cchName`  
 <span data-ttu-id="d06eb-113">[in] 크기 (바이트)의 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-113">[in] The size, in bytes, of `szName`.</span></span>  
  
 `pcName`  
 <span data-ttu-id="d06eb-114">[out] 에 실제로 반환 된 문자 수가 `szName`합니다.</span><span class="sxs-lookup"><span data-stu-id="d06eb-114">[out] The number of characters actually returned in `szName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d06eb-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d06eb-115">Requirements</span></span>  
 <span data-ttu-id="d06eb-116">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d06eb-116">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d06eb-117">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d06eb-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d06eb-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d06eb-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d06eb-119">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d06eb-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d06eb-120">참고자료</span><span class="sxs-lookup"><span data-stu-id="d06eb-120">See also</span></span>
- [<span data-ttu-id="d06eb-121">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d06eb-121">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="d06eb-122">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d06eb-122">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
