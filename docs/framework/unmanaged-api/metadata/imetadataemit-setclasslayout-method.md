---
title: IMetaDataEmit::SetClassLayout 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetClassLayout
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetClassLayout
helpviewer_keywords:
- IMetaDataEmit::SetClassLayout method [.NET Framework metadata]
- SetClassLayout method [.NET Framework metadata]
ms.assetid: 2576c449-388d-4434-a0e1-9f53991e11b6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 80bf9de3eb274bf536b2794ba2ed14e7e9b553cc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59157705"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="bdb0d-102">IMetaDataEmit::SetClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="bdb0d-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="bdb0d-103">에 대 한 이전 호출에서 정의 된 클래스에 대 한 필드 레이아웃을 완료 [DefineTypeDef 메서드](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdb0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="bdb0d-104">Syntax</span></span>  
  
```  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,   
    [in]  DWORD               dwPackSize,   
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],   
    [in]  ULONG               ulClassSize   
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="bdb0d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="bdb0d-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="bdb0d-106">[in] `mdTypeDef` 배치 클래스를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="bdb0d-107">[in] 압축 크기: 1, 2, 4, 8 또는 16 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="bdb0d-108">압축 크기가 인접 한 필드 사이의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="bdb0d-109">[in] 배열을 [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) 구조를 각각 클래스 내에서 클래스의 필드와 필드 오프셋을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="bdb0d-110">배열 종료 `mdTokenNil`합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="bdb0d-111">[in] 클래스의 바이트 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bdb0d-112">설명</span><span class="sxs-lookup"><span data-stu-id="bdb0d-112">Remarks</span></span>  
 <span data-ttu-id="bdb0d-113">클래스가 호출 하 여 처음에 정의 되는 [imetadataemit:: Definetypedef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드 및 클래스의 필드에 대 한 세 가지 레이아웃 중 하나를 지정: 자동, 순차적으로 또는 명시적입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="bdb0d-114">일반적으로 자동 레이아웃을 사용 하는 공용 언어 런타임이 가장 좋은 방법은 필드 레이아웃을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="bdb0d-115">그러나 코드는 관리 되지 않는 정렬에 따라 배치 필드 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="bdb0d-116">이 경우 sequential 또는 explicit 레이아웃 및 호출을 선택 `SetClassLayout` 필드의 레이아웃을 완료 하려면:</span><span class="sxs-lookup"><span data-stu-id="bdb0d-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
-   <span data-ttu-id="bdb0d-117">순차적 레이아웃: 압축 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="bdb0d-118">필드는 자연 스러운 크기 또는 어떤 결과 필드의 작은 오프셋의 압축 크기에 따라 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="bdb0d-119">설정할 `rFieldOffsets` 고 `ulClassSize` 0입니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
-   <span data-ttu-id="bdb0d-120">명시적 레이아웃: 각 필드의 오프셋을 지정 하거나 클래스와 압축 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdb0d-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bdb0d-121">Requirements</span></span>  
 <span data-ttu-id="bdb0d-122">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="bdb0d-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bdb0d-123">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="bdb0d-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="bdb0d-124">**라이브러리:** MSCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="bdb0d-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bdb0d-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="bdb0d-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdb0d-126">참고자료</span><span class="sxs-lookup"><span data-stu-id="bdb0d-126">See also</span></span>

- [<span data-ttu-id="bdb0d-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdb0d-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="bdb0d-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="bdb0d-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
