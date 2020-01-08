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
ms.openlocfilehash: ef7057ad19fd34750bd15d358e9c1ebb1289cd44
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/25/2019
ms.locfileid: "75338058"
---
# <a name="imetadataimportenuminterfaceimpls-method"></a><span data-ttu-id="7ade5-102">IMetaDataImport::EnumInterfaceImpls 메서드</span><span class="sxs-lookup"><span data-stu-id="7ade5-102">IMetaDataImport::EnumInterfaceImpls Method</span></span>
<span data-ttu-id="7ade5-103">지정 된 `TypeDef`에서 구현 하는 모든 인터페이스를 열거 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-103">Enumerates all interfaces implemented by the specified `TypeDef`.</span></span> 
  
## <a name="syntax"></a><span data-ttu-id="7ade5-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ade5-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumInterfaceImpls (  
   [in, out]  HCORENUM       *phEnum,   
   [in]   mdTypeDef          td,  
   [out]  mdInterfaceImpl    rImpls[],   
   [in]   ULONG              cMax,  
   [out]  ULONG*             pcImpls  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7ade5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7ade5-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7ade5-106">[in, out] 열거자에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-106">[in, out] A pointer to the enumerator.</span></span>  
  
 `td`  
 <span data-ttu-id="7ade5-107">진행 인터페이스 구현을 나타내는 MethodDef 토큰이 열거 될 TypeDef의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-107">[in] The token of the TypeDef whose MethodDef tokens representing interface implementations are to be enumerated.</span></span>  
  
 `rImpls`  
 <span data-ttu-id="7ade5-108">제한이 MethodDef 토큰을 저장 하는 데 사용 되는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-108">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7ade5-109">진행 `rImpls` 배열의 최대 길이입니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-109">[in] The maximum length of the `rImpls` array.</span></span>  
  
 `pcImpls`  
 <span data-ttu-id="7ade5-110">제한이 `rImpls`에서 반환 된 실제 토큰 수입니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-110">[out] The actual number of tokens returned in `rImpls`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7ade5-111">반환 값</span><span class="sxs-lookup"><span data-stu-id="7ade5-111">Return Value</span></span>  
  
|<span data-ttu-id="7ade5-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7ade5-112">HRESULT</span></span>|<span data-ttu-id="7ade5-113">설명</span><span class="sxs-lookup"><span data-stu-id="7ade5-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7ade5-114">`EnumInterfaceImpls` 성공적으로 반환 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-114">`EnumInterfaceImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7ade5-115">열거할 MethodDef 토큰이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-115">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="7ade5-116">이 경우 `pcImpls`은 0으로 설정 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-116">In that case, `pcImpls` is set to zero.</span></span>|  

## <a name="remarks"></a><span data-ttu-id="7ade5-117">주의</span><span class="sxs-lookup"><span data-stu-id="7ade5-117">Remarks</span></span>

<span data-ttu-id="7ade5-118">열거형은 지정 된 `TypeDef`에서 구현 하는 각 인터페이스에 대 한 `mdInterfaceImpl` 토큰의 컬렉션을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-118">The enumeration returns a collection of `mdInterfaceImpl` tokens for each interface implemented by the specified `TypeDef`.</span></span> <span data-ttu-id="7ade5-119">인터페이스 토큰은 인터페이스가 지정 된 순서 (`DefineTypeDef` 또는 `SetTypeDefProps`)로 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-119">Interface tokens are returned in the order the interfaces were specified (through `DefineTypeDef` or `SetTypeDefProps`).</span></span> <span data-ttu-id="7ade5-120">[GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md)를 사용 하 여 반환 된 `mdInterfaceImpl` 토큰의 속성을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-120">Properties of the returned `mdInterfaceImpl` tokens can be queried using [GetInterfaceImplProps](imetadataimport-getinterfaceimplprops-method.md).</span></span>
  
## <a name="requirements"></a><span data-ttu-id="7ade5-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ade5-121">Requirements</span></span>  
 <span data-ttu-id="7ade5-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7ade5-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ade5-123">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="7ade5-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7ade5-124">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7ade5-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7ade5-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ade5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ade5-126">참조</span><span class="sxs-lookup"><span data-stu-id="7ade5-126">See also</span></span>

- [<span data-ttu-id="7ade5-127">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ade5-127">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7ade5-128">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="7ade5-128">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
