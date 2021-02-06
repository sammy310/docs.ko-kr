---
description: '자세히 알아보기: IMetaDataImport:: EnumInterfaceImpls 메서드'
title: IMetaDataImport::EnumInterfaceImpls 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumInterfaceImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumInterfaceImpls
helpviewer_keywords:
- IMetaDataImport::EnumInterfaceImpls method [.NET Framework metadata]
- EnumInterfaceImpls method [.NET Framework metadata]
ms.assetid: ba6e178f-128b-4e47-a13c-b4be73eb106c
topic_type:
- apiref
ms.openlocfilehash: 5276d1edb3be0cae76b18a06241dc6b9952e1a72
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649418"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="91d6b-103">IMetaDataImport::EnumInterfaceImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="91d6b-103">IMetaDataImport::EnumInterfaceImpls Method</span></span>

<span data-ttu-id="91d6b-104">지정 된에 의해 구현 된 모든 인터페이스를 열거 `TypeDef` 합니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-104">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="91d6b-105">구문</span><span class="sxs-lookup"><span data-stu-id="91d6b-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="91d6b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="91d6b-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="91d6b-107">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-107">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="91d6b-108">진행 인터페이스 구현을 나타내는 MethodDef 토큰이 열거 될 TypeDef의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-108">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="91d6b-109">제한이 MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-109">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="91d6b-110">진행 배열의 최대 길이 `rImpls` 입니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-110">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="91d6b-111">제한이 에서 반환 된 실제 토큰 수 `rImpls` 입니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-111">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="91d6b-112">Return Value</span><span class="sxs-lookup"><span data-stu-id="91d6b-112">Return Value</span></span>  
  
|<span data-ttu-id="91d6b-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="91d6b-113">HRESULT</span></span>|<span data-ttu-id="91d6b-114">설명</span><span class="sxs-lookup"><span data-stu-id="91d6b-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="91d6b-115">`EnumInterfaceImpls` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-115">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="91d6b-116">열거할 MethodDef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="91d6b-117">`pcImpls`이 경우는 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-117">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="91d6b-118">설명</span><span class="sxs-lookup"><span data-stu-id="91d6b-118">Remarks</span></span>

<span data-ttu-id="91d6b-119">열거형은 `mdInterfaceImpl` 지정 된에 의해 구현 되는 각 인터페이스에 대 한 토큰의 컬렉션을 반환 합니다 `TypeDef` .</span><span class="sxs-lookup"><span data-stu-id="91d6b-119">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="91d6b-120">인터페이스 토큰은 인터페이스가 지정 된 순서 (또는)로 반환 됩니다 `DefineTypeDef` `SetTypeDefProps` .</span><span class="sxs-lookup"><span data-stu-id="91d6b-120">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="91d6b-121">반환 된 토큰의 속성은 `mdInterfaceImpl` [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)를 사용 하 여 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-121">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="91d6b-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="91d6b-122">Requirements</span></span>  

 <span data-ttu-id="91d6b-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="91d6b-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="91d6b-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="91d6b-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="91d6b-125">**라이브러리:** MsCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="91d6b-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="91d6b-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="91d6b-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="91d6b-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="91d6b-127">See also</span></span>

- [<span data-ttu-id="91d6b-128">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91d6b-128">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="91d6b-129">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="91d6b-129">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
