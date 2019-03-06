---
title: IMetaDataEmit::DefineParam 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.DefineParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::DefineParam
helpviewer_keywords:
- IMetaDataEmit::DefineParam method [.NET Framework metadata]
- DefineParam method [.NET Framework metadata]
ms.assetid: d86a3d14-4796-4909-9591-dfafe3de5ce4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5384dd69578dbd912690b9490bd4bfa762ccd56d
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57475309"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="5108c-102">IMetaDataEmit::DefineParam 메서드</span><span class="sxs-lookup"><span data-stu-id="5108c-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="5108c-103">지정한 시그니처를 지정된 된 토큰에서 참조 하는 메서드를 사용 하 여 매개 변수 정의 만들고 해당 매개 변수 정의 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5108c-104">구문</span><span class="sxs-lookup"><span data-stu-id="5108c-104">Syntax</span></span>  
  
```  
HRESULT DefineParam (  
    [in]  mdMethodDef md,   
    [in]  ULONG       ulParamSeq,   
    [in]  LPCWSTR     szName,   
    [in]  DWORD       dwParamFlags,   
    [in]  DWORD       dwCPlusTypeFlag,   
    [in]  void const  *pValue,  
    [in]  ULONG       cchValue,   
    [out] mdParamDef  *ppd   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5108c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5108c-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="5108c-106">[in] 매개 변수를 정의 하는 메서드에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="5108c-107">[in] 매개 변수 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="5108c-108">[in] 유니코드에서 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="5108c-109">[in] 플래그 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="5108c-110">이 비트 마스크의 `CorParamAttr` 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="5108c-111">[in] `ELEMENT_TYPE_` *\** 상수 값에 대 한 합니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="5108c-112">[in] 매개 변수에 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="5108c-113">[in] 유니코드 문자에서 크기의 `pValue`합니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="5108c-114">[out] `mdParamDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5108c-115">설명</span><span class="sxs-lookup"><span data-stu-id="5108c-115">Remarks</span></span>  
 <span data-ttu-id="5108c-116">시퀀스 값 `ulParamSeq` 매개 변수에 대 한 1부터 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="5108c-117">반환 값에 0의 시퀀스 번호가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5108c-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5108c-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5108c-118">Requirements</span></span>  
 <span data-ttu-id="5108c-119">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5108c-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5108c-120">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5108c-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5108c-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5108c-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5108c-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5108c-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5108c-123">참고자료</span><span class="sxs-lookup"><span data-stu-id="5108c-123">See also</span></span>
- [<span data-ttu-id="5108c-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5108c-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="5108c-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5108c-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
