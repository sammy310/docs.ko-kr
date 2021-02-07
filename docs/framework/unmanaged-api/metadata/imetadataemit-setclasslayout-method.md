---
description: '자세히 알아보기: IMetaDataEmit:: SetClassLayout 메서드'
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
ms.openlocfilehash: e0ce8e93137b9a32a13ca86ead539385523fa8a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99706606"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="450c5-103">IMetaDataEmit::SetClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="450c5-103">IMetaDataEmit::SetClassLayout Method</span></span>

<span data-ttu-id="450c5-104">지정 된 클래스에 대 한 필드의 [레이아웃을 완료 합니다.](imetadataemit-definetypedef-method.md)</span><span class="sxs-lookup"><span data-stu-id="450c5-104">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="450c5-105">구문</span><span class="sxs-lookup"><span data-stu-id="450c5-105">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="450c5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="450c5-106">Parameters</span></span>  

 `td`  
 <span data-ttu-id="450c5-107">진행 `mdTypeDef` 레이아웃을 지정할 클래스를 지정 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-107">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="450c5-108">진행 압축 크기는 1, 2, 4, 8 또는 16 바이트입니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-108">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="450c5-109">압축 크기는 인접 한 필드 사이의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-109">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="450c5-110">진행 각각 클래스의 필드와 클래스 내의 필드 오프셋을 지정 하는 [COR_FIELD_OFFSET](cor-field-offset-structure.md) 구조체의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-110">[in] An array of [COR_FIELD_OFFSET](cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="450c5-111">를 사용 하 여 배열을 종료 `mdTokenNil` 합니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-111">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="450c5-112">진행 클래스의 크기 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-112">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="450c5-113">설명</span><span class="sxs-lookup"><span data-stu-id="450c5-113">Remarks</span></span>  

 <span data-ttu-id="450c5-114">클래스는 [IMetaDataEmit::D Efin def](imetadataemit-definetypedef-method.md) 메서드를 호출 하 고 클래스의 필드에 대 한 세 가지 레이아웃 (자동, 순차 또는 명시적) 중 하나를 지정 하 여 처음에 정의 됩니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-114">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="450c5-115">일반적으로 자동 레이아웃을 사용 하 고 런타임에 필드의 레이아웃을 지정 하는 가장 좋은 방법을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-115">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="450c5-116">그러나 비관리 코드에서 사용 하는 배열에 따라 필드가 배치 되도록 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-116">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="450c5-117">이 경우 순차 또는 명시적 레이아웃 중 하나를 선택 하 고를 호출 `SetClassLayout` 하 여 필드 레이아웃을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-117">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="450c5-118">순차 레이아웃: 압축 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-118">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="450c5-119">필드는 자연 크기 또는 압축 크기에 따라 정렬 되며 필드의 오프셋은 더 작은 값으로 정렬 됩니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-119">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="450c5-120">`rFieldOffsets`및 `ulClassSize` 를 0으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-120">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="450c5-121">명시적 레이아웃: 각 필드의 오프셋을 지정 하거나 클래스 크기와 압축 크기를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-121">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="450c5-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="450c5-122">Requirements</span></span>  

 <span data-ttu-id="450c5-123">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="450c5-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="450c5-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="450c5-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="450c5-125">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="450c5-125">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="450c5-126">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="450c5-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="450c5-127">참고 항목</span><span class="sxs-lookup"><span data-stu-id="450c5-127">See also</span></span>

- [<span data-ttu-id="450c5-128">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="450c5-128">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="450c5-129">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="450c5-129">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
