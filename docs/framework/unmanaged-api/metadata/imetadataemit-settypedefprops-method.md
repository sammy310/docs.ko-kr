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
ms.openlocfilehash: e59e7695246b2c83171e77352e16464258516f8d
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177459"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="82545-102">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="82545-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="82545-103">[IMetaDataEmit::DefineTypeDef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대한 사전 호출에 의해 정의된 형식의 기능을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="82545-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="82545-104">구문</span><span class="sxs-lookup"><span data-stu-id="82545-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="82545-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="82545-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="82545-106">【인】 `mdTypeDef` [IMetaDataEmit::DefineTypeDef에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대한 원래 호출에서 얻은 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="82545-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="82545-107">【인】 `TypeDef` 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="82545-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="82545-108">이것은 값의 `CorTypeAttr` 비트 마스크입니다.</span><span class="sxs-lookup"><span data-stu-id="82545-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="82545-109">【인】 기본 `mdToken` 클래스의 입니다.</span><span class="sxs-lookup"><span data-stu-id="82545-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="82545-110">[IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md)에 대한 이전 호출에서 `null`얻은 또는 .</span><span class="sxs-lookup"><span data-stu-id="82545-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="82545-111">【인】 이 형식이 구현하는 인터페이스에 대한 토큰 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="82545-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="82545-112">이러한 `mdTypeRef` 토큰은 [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span><span class="sxs-lookup"><span data-stu-id="82545-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="82545-113">배열의 마지막 요소는 .가 `mdTokenNil`있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="82545-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="82545-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="82545-114">Requirements</span></span>  
 <span data-ttu-id="82545-115">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="82545-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="82545-116">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="82545-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="82545-117">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="82545-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="82545-118">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="82545-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="82545-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="82545-119">See also</span></span>

- [<span data-ttu-id="82545-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82545-120">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="82545-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="82545-121">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
