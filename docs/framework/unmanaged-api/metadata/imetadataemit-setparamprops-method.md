---
title: IMetaDataEmit::SetParamProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetParamProps
helpviewer_keywords:
- IMetaDataEmit::SetParamProps method [.NET Framework metadata]
- SetParamProps method [.NET Framework metadata]
ms.assetid: a95a3908-9f87-4084-937e-8e01ef03ad63
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f8448de17ad974bc77021a7880b7d8576c69ae75
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67750917"
---
# <a name="imetadataemitsetparamprops-method"></a><span data-ttu-id="82506-102">IMetaDataEmit::SetParamProps 메서드</span><span class="sxs-lookup"><span data-stu-id="82506-102">IMetaDataEmit::SetParamProps Method</span></span>
<span data-ttu-id="82506-103">설정 하거나 변경 기능에 대 한 이전 호출에서 정의 된 메서드 매개 변수의 [imetadataemit:: Defineparam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="82506-103">Sets or changes features of a method parameter that was defined by a prior call to [IMetaDataEmit::DefineParam](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineparam-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82506-104">구문</span><span class="sxs-lookup"><span data-stu-id="82506-104">Syntax</span></span>  
  
```cpp  
HRESULT SetParamProps (   
    [in]  mdParamDef  pd,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,   
    [in]  ULONG       cchValue   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82506-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82506-105">Parameters</span></span>  
 `pd`  
 <span data-ttu-id="82506-106">[in] 대상 매개 변수에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="82506-106">[in] The token for the target parameter.</span></span>  
  
 `szName`  
 <span data-ttu-id="82506-107">[in] 유니코드에서 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="82506-107">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="82506-108">[in] 매개 변수는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="82506-108">[in] The flags for the parameter.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="82506-109">[in] ELEMENT_TYPE_ \* 상수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="82506-109">[in] The ELEMENT_TYPE_\* for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="82506-110">[in] 매개 변수에 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="82506-110">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="82506-111">[in] \(유니코드) 문자의 크기 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="82506-111">[in] The size in (Unicode) characters of `pValue`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82506-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82506-112">Requirements</span></span>  
 <span data-ttu-id="82506-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="82506-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82506-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="82506-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82506-115">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="82506-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82506-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82506-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82506-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="82506-117">See also</span></span>

- [<span data-ttu-id="82506-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82506-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="82506-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82506-119">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
