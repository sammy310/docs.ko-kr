---
description: IMetaDataEmit::D efineParam 메서드에 대해 자세히 알아보세요.
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
ms.openlocfilehash: 300de3183b329773a8e6813d6b92c6d049d63195
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784095"
---
# <a name="imetadataemitdefineparam-method"></a><span data-ttu-id="ae256-103">IMetaDataEmit::DefineParam 메서드</span><span class="sxs-lookup"><span data-stu-id="ae256-103">IMetaDataEmit::DefineParam Method</span></span>

<span data-ttu-id="ae256-104">지정 된 토큰이 참조 하는 메서드에 대해 지정 된 서명을 사용 하 여 매개 변수 정의를 만들고 해당 매개 변수 정의에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-104">Creates a parameter definition with the specified signature for the method referenced by the specified token, and gets a token for that parameter definition.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae256-105">구문</span><span class="sxs-lookup"><span data-stu-id="ae256-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="ae256-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae256-106">Parameters</span></span>  

 `md`  
 <span data-ttu-id="ae256-107">진행 매개 변수가 정의 되 고 있는 메서드의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-107">[in] The token for the method whose parameter is being defined.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="ae256-108">진행 매개 변수 시퀀스 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-108">[in] The parameter sequence number.</span></span>  
  
 `szName`  
 <span data-ttu-id="ae256-109">진행 유니코드의 매개 변수 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-109">[in] The name of the parameter in Unicode.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="ae256-110">진행 매개 변수에 대 한 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-110">[in] Flags for the parameter.</span></span> <span data-ttu-id="ae256-111">값의 비트 마스크입니다 `CorParamAttr` .</span><span class="sxs-lookup"><span data-stu-id="ae256-111">This is a bitmask of `CorParamAttr` values.</span></span>  
  
 `dwCPlusTypeFlag`  
 <span data-ttu-id="ae256-112">[in] `ELEMENT_TYPE_` *\** 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-112">[in] `ELEMENT_TYPE_`*\** for the constant value.</span></span>  
  
 `pValue`  
 <span data-ttu-id="ae256-113">진행 매개 변수에 대 한 상수 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-113">[in] The constant value for the parameter.</span></span>  
  
 `cchValue`  
 <span data-ttu-id="ae256-114">진행 의 유니코드 문자 크기입니다 `pValue` .</span><span class="sxs-lookup"><span data-stu-id="ae256-114">[in] The size, in Unicode characters, of `pValue`.</span></span>  
  
 `ppd`  
 <span data-ttu-id="ae256-115">제한이 `mdParamDef` 할당 된 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-115">[out] The `mdParamDef` token assigned.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ae256-116">설명</span><span class="sxs-lookup"><span data-stu-id="ae256-116">Remarks</span></span>  

 <span data-ttu-id="ae256-117">매개 변수의 시퀀스 값은 `ulParamSeq` 1로 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-117">The sequence values in `ulParamSeq` begin with 1 for parameters.</span></span> <span data-ttu-id="ae256-118">반환 값의 시퀀스 번호는 0입니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-118">A return value has a sequence number of 0.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae256-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae256-119">Requirements</span></span>  

 <span data-ttu-id="ae256-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ae256-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ae256-121">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ae256-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ae256-122">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ae256-122">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ae256-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ae256-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae256-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ae256-124">See also</span></span>

- [<span data-ttu-id="ae256-125">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae256-125">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="ae256-126">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae256-126">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
