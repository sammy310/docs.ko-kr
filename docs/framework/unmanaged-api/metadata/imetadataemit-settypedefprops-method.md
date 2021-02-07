---
description: '자세히 알아보기: IMetaDataEmit:: SetTypeDefProps 메서드'
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
ms.openlocfilehash: 1160d20e7ceb422390f8cd725a75fdb4f42318e7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706502"
---
# <a name="imetadataemitsettypedefprops-method"></a><span data-ttu-id="c67e4-103">IMetaDataEmit::SetTypeDefProps 메서드</span><span class="sxs-lookup"><span data-stu-id="c67e4-103">IMetaDataEmit::SetTypeDefProps Method</span></span>

<span data-ttu-id="c67e4-104">[IMetaDataEmit:D](imetadataemit-definetypedef-method.md)에 대 한 이전 호출로 정의 된 형식의 기능을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c67e4-104">Sets features of a type defined by a prior call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c67e4-105">구문</span><span class="sxs-lookup"><span data-stu-id="c67e4-105">Syntax</span></span>  
  
```cpp  
HRESULT SetTypeDefProps (  
    [in]  mdTypeDef   td,
    [in]  DWORD       dwTypeDefFlags,
    [in]  mdToken     tkExtends,
    [in]  mdToken     rtkImplements[]
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c67e4-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c67e4-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="c67e4-107">진행 `mdTypeDef` IMetaDataEmit에 대 한 원래 호출에서 가져온 토큰 [::D efin을 정의](imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="c67e4-107">[in] An `mdTypeDef` token obtained from original call to [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md).</span></span>  
  
 `dwTypeDefFlags`  
 <span data-ttu-id="c67e4-108">[in] `TypeDef` 특성.</span><span class="sxs-lookup"><span data-stu-id="c67e4-108">[in] `TypeDef` attributes.</span></span> <span data-ttu-id="c67e4-109">값의 비트 마스크입니다 `CorTypeAttr` .</span><span class="sxs-lookup"><span data-stu-id="c67e4-109">This is a bitmask of `CorTypeAttr` values.</span></span>  
  
 `tkExtends`  
 <span data-ttu-id="c67e4-110">진행 `mdToken` 기본 클래스의입니다.</span><span class="sxs-lookup"><span data-stu-id="c67e4-110">[in] The `mdToken` of the base class.</span></span> <span data-ttu-id="c67e4-111">IMetaDataEmit에 대 한 이전 호출에서 가져옵니다. [:D efineImportType](imetadataemit-defineimporttype-method.md)또는 `null` .</span><span class="sxs-lookup"><span data-stu-id="c67e4-111">Obtained from a previous call to [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md), or `null`.</span></span>  
  
 `rtkImplements[]`  
 <span data-ttu-id="c67e4-112">진행 이 형식이 구현 하는 인터페이스에 대 한 토큰의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="c67e4-112">[in] An array of tokens for the interfaces that this type implements.</span></span> <span data-ttu-id="c67e4-113">이러한 `mdTypeRef` 토큰은 [IMetaDataEmit::D efineImportType](imetadataemit-defineimporttype-method.md)을 사용 하 여 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c67e4-113">These `mdTypeRef` tokens are obtained using [IMetaDataEmit::DefineImportType](imetadataemit-defineimporttype-method.md).</span></span> <span data-ttu-id="c67e4-114">배열의 마지막 요소는 이어야 합니다 `mdTokenNil` .</span><span class="sxs-lookup"><span data-stu-id="c67e4-114">The last element of the array is must be `mdTokenNil`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c67e4-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c67e4-115">Requirements</span></span>  

 <span data-ttu-id="c67e4-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c67e4-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c67e4-117">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c67e4-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c67e4-118">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c67e4-118">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c67e4-119">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c67e4-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c67e4-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c67e4-120">See also</span></span>

- [<span data-ttu-id="c67e4-121">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c67e4-121">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="c67e4-122">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c67e4-122">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
