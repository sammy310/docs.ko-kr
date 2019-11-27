---
title: IMetaDataEmit::SetTypeDefProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetTypeDefProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetTypeDefProps
helpviewer_keywords:
- SetTypeDefProps method [.NET Framework metadata]
- IMetaDataEmit::SetTypeDefProps method [.NET Framework metadata]
ms.assetid: 480d596a-759f-4d29-ac1a-3dbff8f3544d
topic_type:
- apiref
ms.openlocfilehash: 3ab29fc8c983b354ad5088d26c547868940ec70a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74447721"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="1cb7a-102">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="1cb7a-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="1cb7a-103">[IMetaDataEmit:D](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)에 대 한 이전 호출로 정의 된 형식의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1cb7a-104">구문</span><span class="sxs-lookup"><span data-stu-id="1cb7a-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,   
    [in]  DWORD       dwTypeDefFlags,   
    [in]  mdToken     tkExtends,   
    [in]  mdToken     rtkImplements[]   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1cb7a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1cb7a-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="1cb7a-106">진행 [IMetaDataEmit::D Efin](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)에 대 한 원래 호출에서 가져온 `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="1cb7a-107">[in] `TypeDef` 특성입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="1cb7a-108">`CorTypeAttr` 값의 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="1cb7a-109">진행 기본 클래스의 `mdToken`입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="1cb7a-110">IMetaDataEmit에 대 한 이전 호출에서 가져옵니다 [.:D efineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)또는 `null`.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="1cb7a-111">진행 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="1cb7a-112">이러한 `mdTypeRef` 토큰은 [IMetaDataEmit::D efineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)을 사용 하 여 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="1cb7a-113">배열의 마지막 요소는 `mdTokenNil`이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="1cb7a-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1cb7a-114">Requirements</span></span>  
 <span data-ttu-id="1cb7a-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1cb7a-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="1cb7a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1cb7a-117">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1cb7a-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1cb7a-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1cb7a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1cb7a-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1cb7a-119">See also</span></span>

- [<span data-ttu-id="1cb7a-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1cb7a-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="1cb7a-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1cb7a-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
