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
ms.openlocfilehash: 2807458549db02598ba05f2aa80fa6ea6fbc5a13
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177701"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="b18c2-102">IMetaDataEmit::DefineParam 메서드</span><span class="sxs-lookup"><span data-stu-id="b18c2-102">IMetaDataEmit::DefineParam Method</span></span>
<span data-ttu-id="b18c2-103">지정된 토큰에서 참조하는 메서드에 대해 지정된 시그니처를 사용하여 매개 변수 정의를 만들고 해당 매개 변수 정의에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b18c2-104">구문</span><span class="sxs-lookup"><span data-stu-id="b18c2-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="b18c2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b18c2-105">Parameters</span></span>  
 `md`  
 <span data-ttu-id="b18c2-106">【인】 매개 변수가 정의되는 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="b18c2-107">【인】 매개 변수 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="b18c2-108">【인】 유니코드의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="b18c2-109">【인】 매개 변수에 대한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="b18c2-110">이것은 값의 `CorParamAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="b18c2-111">【인】 `ELEMENT_TYPE_` 상수 값에 대한 값입니다. *\**</span><span class="sxs-lookup"><span data-stu-id="b18c2-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="b18c2-112">【인】 매개 변수의 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="b18c2-113">【인】 유니코드 문자의 크기입니다. `pValue`</span><span class="sxs-lookup"><span data-stu-id="b18c2-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="b18c2-114">【아웃】 할당된 토큰입니다. `mdParamDef`</span><span class="sxs-lookup"><span data-stu-id="b18c2-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b18c2-115">설명</span><span class="sxs-lookup"><span data-stu-id="b18c2-115">Remarks</span></span>  
 <span data-ttu-id="b18c2-116">시퀀스 `ulParamSeq` 값은 매개변수에 대해 1로 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="b18c2-117">반환 값에는 시퀀스 번호가 0입니다.</span><span class="sxs-lookup"><span data-stu-id="b18c2-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b18c2-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b18c2-118">Requirements</span></span>  
 <span data-ttu-id="b18c2-119">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b18c2-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b18c2-120">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="b18c2-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b18c2-121">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b18c2-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b18c2-122">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b18c2-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b18c2-123">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b18c2-123">See also</span></span>

- [<span data-ttu-id="b18c2-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b18c2-124">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b18c2-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b18c2-125">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
