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
ms.openlocfilehash: b05527f118de059c674ea659b1a22b7895126cf4
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007769"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="e5337-102">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="e5337-102">IMetaDataEmit::SetTypeDefProps Method</span></span>
<span data-ttu-id="e5337-103">[IMetaDataEmit:D](imetadataemit-definetypedef-method.md)에 대 한 이전 호출로 정의 된 형식의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5337-103">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e5337-104">구문</span><span class="sxs-lookup"><span data-stu-id="e5337-104">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e5337-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e5337-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="e5337-106">진행 `mdTypeDef`IMetaDataEmit에 대 한 원래 호출에서 가져온 토큰 [::D efin을 정의](imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="e5337-106">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="e5337-107">[in] `TypeDef` 특성.</span><span class="sxs-lookup"><span data-stu-id="e5337-107">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="e5337-108">값의 비트 마스크입니다 `CorTypeAttr` .</span><span class="sxs-lookup"><span data-stu-id="e5337-108">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="e5337-109">진행 `mdToken`기본 클래스의입니다.</span><span class="sxs-lookup"><span data-stu-id="e5337-109">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="e5337-110">IMetaDataEmit에 대 한 이전 호출에서 가져옵니다. [:D efineImportType](imetadataemit-defineimporttype-method.md)또는 `null` .</span><span class="sxs-lookup"><span data-stu-id="e5337-110">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="e5337-111">진행 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="e5337-111">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="e5337-112">이러한 `mdTypeRef` 토큰은 [IMetaDataEmit::D efineImportType](imetadataemit-defineimporttype-method.md)을 사용 하 여 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e5337-112">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="e5337-113">배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="e5337-113">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e5337-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e5337-114">Requirements</span></span>  
 <span data-ttu-id="e5337-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5337-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e5337-116">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="e5337-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e5337-117">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5337-117">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e5337-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e5337-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e5337-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5337-119">See also</span></span>

- [<span data-ttu-id="e5337-120">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5337-120">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="e5337-121">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e5337-121">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
