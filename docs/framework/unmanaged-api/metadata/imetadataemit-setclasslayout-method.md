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
ms.openlocfilehash: e855868d18fc6cffdd5d92cfa401606caf45b76c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177566"
---
# <a name="imetadataemitsetclasslayout-method"></a><span data-ttu-id="de814-102">IMetaDataEmit::SetClassLayout 메서드</span><span class="sxs-lookup"><span data-stu-id="de814-102">IMetaDataEmit::SetClassLayout Method</span></span>
<span data-ttu-id="de814-103">[정의TypeDef 메서드에](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md)대 한 사전 호출에 의해 정의 된 클래스에 대 한 필드의 레이아웃을 완료 합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-103">Completes the layout of fields for a class that has been defined by a prior call to [DefineTypeDef Method](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de814-104">구문</span><span class="sxs-lookup"><span data-stu-id="de814-104">Syntax</span></span>  
  
```cpp  
HRESULT SetClassLayout (  
    [in]  mdTypeDef           td,
    [in]  DWORD               dwPackSize,
    [in]  COR_FIELD_OFFSET    rFieldOffsets[],
    [in]  ULONG               ulClassSize
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="de814-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de814-105">Parameters</span></span>  
 `td`  
 <span data-ttu-id="de814-106">【인】 배치할 클래스를 지정하는 `mdTypeDef` 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="de814-106">[in] An `mdTypeDef` token that specifies the class to be laid out.</span></span>  
  
 `dwPackSize`  
 <span data-ttu-id="de814-107">【인】 포장 크기: 1, 2, 4, 8 또는 16 바이트.</span><span class="sxs-lookup"><span data-stu-id="de814-107">[in] The packing size: 1, 2, 4, 8 or 16 bytes.</span></span> <span data-ttu-id="de814-108">압축 크기는 인접 필드 사이의 바이트 수입니다.</span><span class="sxs-lookup"><span data-stu-id="de814-108">The packing size is the number of bytes between adjacent fields.</span></span>  
  
 `rFieldOffsets`  
 <span data-ttu-id="de814-109">【인】 [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) 구조의 배열로, 각 구조는 클래스의 필드와 클래스 내의 필드의 오프셋을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-109">[in] An array of [COR_FIELD_OFFSET](../../../../docs/framework/unmanaged-api/metadata/cor-field-offset-structure.md) structures, each of which specifies a field of the class and the field's offset within the class.</span></span> <span data-ttu-id="de814-110">을 통해 `mdTokenNil`배열을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-110">Terminate the array with `mdTokenNil`.</span></span>  
  
 `ulClassSize`  
 <span data-ttu-id="de814-111">【인】 클래스의 크기(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="de814-111">[in] The size, in bytes, of the class.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="de814-112">설명</span><span class="sxs-lookup"><span data-stu-id="de814-112">Remarks</span></span>  
 <span data-ttu-id="de814-113">클래스는 처음에 [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) 메서드를 호출 하 고 클래스의 필드에 대 한 세 가지 레이아웃 중 하나를 지정 하 여 정의: 자동, 순차적 또는 명시적.</span><span class="sxs-lookup"><span data-stu-id="de814-113">The class is initially defined by calling the [IMetaDataEmit::DefineTypeDef](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definetypedef-method.md) method, and specifying one of three layouts for the fields of the class: automatic, sequential, or explicit.</span></span> <span data-ttu-id="de814-114">일반적으로 자동 레이아웃을 사용하고 런타임에서 필드를 배치하는 가장 좋은 방법을 선택하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-114">Normally, you would use automatic layout and let the runtime choose the best way to lay out the fields.</span></span>  
  
 <span data-ttu-id="de814-115">그러나 관리되지 않는 코드가 사용하는 배열에 따라 필드를 배치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de814-115">However, you might want the fields laid out according to the arrangement that unmanaged code uses.</span></span> <span data-ttu-id="de814-116">이 경우 순차 적 또는 명시적 레이아웃을 선택하고 호출하여 `SetClassLayout` 필드의 레이아웃을 완료합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-116">In this case, choose either sequential or explicit layout and call `SetClassLayout` to complete the layout of the fields:</span></span>  
  
- <span data-ttu-id="de814-117">순차 적 레이아웃: 압축 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-117">Sequential layout: Specify the packing size.</span></span> <span data-ttu-id="de814-118">필드는 자연 크기 또는 보압 크기에 따라 정렬되며, 필드의 간격띄우기가 작아지게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="de814-118">A field is aligned according to either its natural size or the packing size, whichever results in the smaller offset of the field.</span></span> <span data-ttu-id="de814-119">설정 `rFieldOffsets` `ulClassSize` 및 0으로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-119">Set `rFieldOffsets` and `ulClassSize` to zero.</span></span>  
  
- <span data-ttu-id="de814-120">명시적 레이아웃: 각 필드의 오프셋을 지정하거나 클래스 크기와 압축 크기를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="de814-120">Explicit layout: Either specify the offset of each field or specify the class size and the packing size.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de814-121">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de814-121">Requirements</span></span>  
 <span data-ttu-id="de814-122">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="de814-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de814-123">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="de814-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="de814-124">**라이브러리:** MSCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="de814-124">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="de814-125">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de814-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de814-126">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de814-126">See also</span></span>

- [<span data-ttu-id="de814-127">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de814-127">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="de814-128">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de814-128">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
