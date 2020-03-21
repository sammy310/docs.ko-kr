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
ms.openlocfilehash: 1868d13a9dbb73dbdf64e49c395bdbff02ce89d4
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177449"
---
# <a name="imetadataemit2definegenericparam-method"></a><span data-ttu-id="18cd7-102">IMetaDataEmit2::DefineGenericParam 메서드</span><span class="sxs-lookup"><span data-stu-id="18cd7-102">IMetaDataEmit2::DefineGenericParam Method</span></span>
<span data-ttu-id="18cd7-103">제네릭 형식 매개 변수에 대한 정의를 만들고 해당 제네릭 형식 매개 변수에 대한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-103">Creates a definition for a generic type parameter, and gets a token to that generic type parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="18cd7-104">구문</span><span class="sxs-lookup"><span data-stu-id="18cd7-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="18cd7-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="18cd7-105">Parameters</span></span>  
 `tk`  
 <span data-ttu-id="18cd7-106">【인】 제네릭 매개 변수를 정의하는 메서드 `mdTypeDef` 또는 생성자(생성자)를 나타내는 또는 `mdMethodDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-106">[in] An `mdTypeDef` or `mdMethodDef` token that represents the method or constructor for which to define a generic parameter.</span></span>  
  
 `ulParamSeq`  
 <span data-ttu-id="18cd7-107">【인】 제네릭 매개 변수의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-107">[in] The index of the generic parameter.</span></span>  
  
 `dwParamFlags`  
 <span data-ttu-id="18cd7-108">【인】 제네릭 매개 변수에 대한 형식을 설명하는 [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-108">[in] A value of the [CorGenericParamAttr](../../../../docs/framework/unmanaged-api/metadata/corgenericparamattr-enumeration.md) enumeration that describes the type for the generic parameter.</span></span>  
  
 `szname`  
 <span data-ttu-id="18cd7-109">【인】 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-109">[in] The name of the parameter.</span></span>  
  
 `reserved`  
 <span data-ttu-id="18cd7-110">【인】 이 매개 변수는 향후 확장성을 위해 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-110">[in] This parameter is reserved for future extensibility.</span></span>  
  
 `rtkConstraints`  
 <span data-ttu-id="18cd7-111">【인】 형식 제약 조건의 0-종단 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-111">[in] A zero-terminated array of type constraints.</span></span> <span data-ttu-id="18cd7-112">배열 멤버는 `mdTypeDef`. `mdTypeRef` `mdTypeSpec`</span><span class="sxs-lookup"><span data-stu-id="18cd7-112">Array members must be an `mdTypeDef`, `mdTypeRef`, or `mdTypeSpec` metadata token.</span></span>  
  
 `pgp`  
 <span data-ttu-id="18cd7-113">【아웃】 제네릭 매개 변수를 나타내는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="18cd7-113">[out] A token that represents the generic parameter.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="18cd7-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="18cd7-114">Requirements</span></span>  
 <span data-ttu-id="18cd7-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="18cd7-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="18cd7-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="18cd7-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="18cd7-117">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="18cd7-117">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="18cd7-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="18cd7-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="18cd7-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18cd7-119">See also</span></span>

- [<span data-ttu-id="18cd7-120">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18cd7-120">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="18cd7-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="18cd7-121">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
