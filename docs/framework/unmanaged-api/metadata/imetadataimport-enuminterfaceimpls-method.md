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
ms.openlocfilehash: b535fdd5027a26cc4dd0eafec9883f0186773dd1
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175501"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="79422-102">IMetaDataImport::EnumInterfaceImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="79422-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="79422-103">지정된 `TypeDef`에 의해 구현된 모든 인터페이스를 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="79422-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span>
  
## <a name="syntax"></a><span data-ttu-id="79422-104">구문</span><span class="sxs-lookup"><span data-stu-id="79422-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="79422-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="79422-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="79422-106">【인, 아웃】 열거형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="79422-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="79422-107">【인】 인터페이스 구현을 나타내는 MethodDef 토큰을 등록해야 하는 TypeDef의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="79422-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="79422-108">【아웃】 MethodDef 토큰을 저장하는 데 사용되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="79422-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="79422-109">【인】 배열의 최대 `rImpls` 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="79422-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="79422-110">【아웃】 에서 반환되는 실제 토큰 `rImpls`수입니다.</span><span class="sxs-lookup"><span data-stu-id="79422-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="79422-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="79422-111">Return Value</span></span>  
  
|<span data-ttu-id="79422-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="79422-112">HRESULT</span></span>|<span data-ttu-id="79422-113">Description</span><span class="sxs-lookup"><span data-stu-id="79422-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="79422-114">`EnumInterfaceImpls`성공적으로 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="79422-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="79422-115">메서드Def 를 등록할 수 있는 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="79422-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="79422-116">이 경우 `pcImpls` 0으로 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="79422-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="79422-117">설명</span><span class="sxs-lookup"><span data-stu-id="79422-117">Remarks</span></span>

<span data-ttu-id="79422-118">열거형은 지정된 `TypeDef`에 `mdInterfaceImpl` 의해 구현된 각 인터페이스에 대한 토큰 컬렉션을 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="79422-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="79422-119">인터페이스 토큰은 인터페이스가 지정된 순서대로 반환됩니다(through `DefineTypeDef` or). `SetTypeDefProps`</span><span class="sxs-lookup"><span data-stu-id="79422-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="79422-120">반환된 `mdInterfaceImpl` 토큰의 속성은 [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)를 사용하여 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="79422-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="79422-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="79422-121">Requirements</span></span>  
 <span data-ttu-id="79422-122">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="79422-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="79422-123">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="79422-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="79422-124">**라이브러리:** MsCorEE.dll의 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="79422-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="79422-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="79422-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="79422-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="79422-126">See also</span></span>

- [<span data-ttu-id="79422-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79422-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="79422-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="79422-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
