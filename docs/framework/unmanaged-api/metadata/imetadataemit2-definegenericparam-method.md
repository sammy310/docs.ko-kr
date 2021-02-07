---
description: IMetaDataEmit2::D efineGenericParam 메서드에 대해 자세히 알아보세요.
title: IMetaDataEmit2::DefineGenericParam 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit2.DefineGenericParam
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit2::DefineGenericParam
helpviewer_keywords:
- IMetaDataEmit2::DefineGenericParam method [.NET Framework metadata]
- DefineGenericParam method [.NET Framework metadata]
ms.assetid: 47b2a3b6-907d-43dc-858d-1ae7dca1316a
topic_type:
- apiref
ms.openlocfilehash: 813661adca162f47a864b19c9754b49072bb4c7b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745790"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="1fc44-103">IMetaDataEmit2::DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="1fc44-103">IMetaDataEmit2::DefineGenericParam Method</span></span>

<span data-ttu-id="1fc44-104">제네릭 형식 매개 변수에 대 한 정의를 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-104">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1fc44-105">구문</span><span class="sxs-lookup"><span data-stu-id="1fc44-105">Syntax</span></span>  
  
```cpp  
HRESULT DefineGenericParam (
    [in]  mdToken         tk,
    [in]  ULONG           ulParamSeq,
    [in]  DWORD           dwParamFlags,
    [in]  LPCWSTR         szname,
    [in]  DWORD           reserved,
    [in]  mdToken         rtkConstraints[],
    [out] mdGenericParam  *pgp  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1fc44-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1fc44-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="1fc44-107">진행 `mdTypeDef` `mdMethodDef` 제네릭 매개 변수를 정의할 메서드나 생성자를 나타내는 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-107">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="1fc44-108">진행 제네릭 매개 변수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-108">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="1fc44-109">진행 제네릭 매개 변수의 형식을 설명 하는 [Corgenericparamattr](corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-109">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="1fc44-110">진행 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-110">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="1fc44-111">진행 이 매개 변수는 나중에 확장할 수 있도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-111">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="1fc44-112">진행 0으로 끝나는 형식의 제약 조건 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-112">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="1fc44-113">배열 멤버는 `mdTypeDef` , `mdTypeRef` 또는 `mdTypeSpec` 메타 데이터 토큰 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-113">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="1fc44-114">제한이 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-114">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1fc44-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1fc44-115">Requirements</span></span>  

 <span data-ttu-id="1fc44-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1fc44-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1fc44-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1fc44-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1fc44-118">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1fc44-118">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1fc44-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1fc44-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1fc44-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1fc44-120">See also</span></span>

- [<span data-ttu-id="1fc44-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fc44-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="1fc44-122">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1fc44-122">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
