---
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
ms.openlocfilehash: e4401ea8a70e7ace8d8efc5e0a6d29f6db51b3df
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503815"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="93f9f-102">IMetaDataEmit2::DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="93f9f-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="93f9f-103">제네릭 형식 매개 변수에 대 한 정의를 만들고 해당 제네릭 형식 매개 변수에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="93f9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="93f9f-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="93f9f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="93f9f-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="93f9f-106">진행 `mdTypeDef` `mdMethodDef` 제네릭 매개 변수를 정의할 메서드나 생성자를 나타내는 또는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="93f9f-107">진행 제네릭 매개 변수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="93f9f-108">진행 제네릭 매개 변수의 형식을 설명 하는 [Corgenericparamattr](corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-108">[in] A value of the [CorGenericParamAttr](corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="93f9f-109">진행 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="93f9f-110">진행 이 매개 변수는 나중에 확장할 수 있도록 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="93f9f-111">진행 0으로 끝나는 형식의 제약 조건 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="93f9f-112">배열 멤버는 `mdTypeDef` , `mdTypeRef` 또는 `mdTypeSpec` 메타 데이터 토큰 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="93f9f-113">제한이 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="93f9f-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="93f9f-114">Requirements</span></span>  
 <span data-ttu-id="93f9f-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="93f9f-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93f9f-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="93f9f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="93f9f-117">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="93f9f-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="93f9f-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="93f9f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93f9f-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="93f9f-119">See also</span></span>

- [<span data-ttu-id="93f9f-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93f9f-120">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
- [<span data-ttu-id="93f9f-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="93f9f-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
