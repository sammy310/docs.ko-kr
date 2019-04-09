---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f6e4be2e05c573ec93cc23c8dd6eccc834b8b848
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59136502"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="1f9b9-102">IMetaDataImport::EnumInterfaceImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="1f9b9-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="1f9b9-103">지정 된 구현 하는 모든 인터페이스를 열거 `TypeDef`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="1f9b9-104">구문</span><span class="sxs-lookup"><span data-stu-id="1f9b9-104">Syntax</span></span>  
  
```  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1f9b9-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1f9b9-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="1f9b9-106">[out에서] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="1f9b9-107">[in] 토큰 인터페이스 구현을 나타내는 MethodDef 토큰 인 열거할는 TypeDef입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="1f9b9-108">[out] MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="1f9b9-109">[in] `rImpls` 배열의 최대 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-109">[in] The maximum size of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="1f9b9-110">[out] 반환 된 토큰의 실제 수 `rImpls`입니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="1f9b9-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="1f9b9-111">Return Value</span></span>  
  
|<span data-ttu-id="1f9b9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="1f9b9-112">HRESULT</span></span>|<span data-ttu-id="1f9b9-113">설명</span><span class="sxs-lookup"><span data-stu-id="1f9b9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumInterfaceImpls` <span data-ttu-id="1f9b9-114">성공적으로 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="1f9b9-115">열거할 MethodDef 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="1f9b9-116">이런 경우 `pcImpls` 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="1f9b9-117">설명</span><span class="sxs-lookup"><span data-stu-id="1f9b9-117">Remarks</span></span>

<span data-ttu-id="1f9b9-118">컬렉션을 반환 하는 열거형 `mdInterfaceImpl` 지정 된 구현 되는 각 인터페이스에 대 한 토큰 `TypeDef`합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="1f9b9-119">인터페이스 토큰 인터페이스를 지정 된 순서 대로 반환 됩니다 (통해 `DefineTypeDef` 또는 `SetTypeDefProps`).</span><span class="sxs-lookup"><span data-stu-id="1f9b9-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="1f9b9-120">반환 된 속성 `mdInterfaceImpl` 토큰을 사용 하 여 쿼리할 수 있습니다 [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="1f9b9-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1f9b9-121">Requirements</span></span>  
 <span data-ttu-id="1f9b9-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="1f9b9-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1f9b9-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="1f9b9-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1f9b9-124">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="1f9b9-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="1f9b9-125">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="1f9b9-125">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="1f9b9-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="1f9b9-126">See also</span></span>

- [<span data-ttu-id="1f9b9-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f9b9-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="1f9b9-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1f9b9-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
