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
ms.openlocfilehash: 5b3f89bb14be0d7128682f8702548545b1e50928
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719530"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="8ade1-102">IMetaDataEmit::DefineParam 메서드</span><span class="sxs-lookup"><span data-stu-id="8ade1-102">IMetaDataEmit::DefineParam Method</span></span>

<span data-ttu-id="8ade1-103">지정 된 토큰이 참조 하는 메서드에 대해 지정 된 서명을 사용 하 여 매개 변수 정의를 만들고 해당 매개 변수 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-103">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8ade1-104">구문</span><span class="sxs-lookup"><span data-stu-id="8ade1-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="8ade1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8ade1-105">Parameters</span></span>  

 `md`  
 <span data-ttu-id="8ade1-106">진행 매개 변수가 정의 되 고 있는 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-106">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="8ade1-107">진행 매개 변수 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-107">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="8ade1-108">진행 유니코드의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-108">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="8ade1-109">진행 매개 변수에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-109">[in] Flags for the parameter.</span></span> <span data-ttu-id="8ade1-110">값의 비트 마스크입니다 `CorParamAttr` .</span><span class="sxs-lookup"><span data-stu-id="8ade1-110">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="8ade1-111">[in] `ELEMENT_TYPE_` *\** 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-111">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="8ade1-112">진행 매개 변수에 대 한 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-112">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="8ade1-113">진행 의 유니코드 문자 크기입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="8ade1-113">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="8ade1-114">제한이 `mdParamDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-114">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8ade1-115">설명</span><span class="sxs-lookup"><span data-stu-id="8ade1-115">Remarks</span></span>  

 <span data-ttu-id="8ade1-116">매개 변수의 시퀀스 값은 `ulParamSeq` 1로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-116">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="8ade1-117">반환 값의 시퀀스 번호는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-117">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8ade1-118">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8ade1-118">Requirements</span></span>  

 <span data-ttu-id="8ade1-119">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8ade1-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8ade1-120">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8ade1-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8ade1-121">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8ade1-121">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8ade1-122">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ade1-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8ade1-123">참조</span><span class="sxs-lookup"><span data-stu-id="8ade1-123">See also</span></span>

- [<span data-ttu-id="8ade1-124">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ade1-124">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="8ade1-125">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8ade1-125">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
