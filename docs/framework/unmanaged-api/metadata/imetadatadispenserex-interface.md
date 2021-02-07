---
description: '자세히 알아보기: IMetaDataDispenserEx 인터페이스'
title: IMetaDataDispenserEx 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx
helpviewer_keywords:
- IMetaDataDispenserEx interface [.NET Framework metadata]
ms.assetid: 78b3629e-77a2-4406-89c3-56b5cc2c4594
topic_type:
- apiref
ms.openlocfilehash: d940ac20eaad4b930ab17fb2d194d3b03bd4cf3c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753538"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="27e24-103">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27e24-103">IMetaDataDispenserEx Interface</span></span>

<span data-ttu-id="27e24-104">[IMetaDataDispenser 인터페이스](imetadatadispenser-interface.md) 인터페이스를 확장 하 여 메타 데이터 api가 현재 메타 데이터 범위에서 작동 하는 방식을 제어할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-104">Extends the [IMetaDataDispenser Interface](imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="27e24-105">메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-105">Methods</span></span>  
  
|<span data-ttu-id="27e24-106">메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-106">Method</span></span>|<span data-ttu-id="27e24-107">설명</span><span class="sxs-lookup"><span data-stu-id="27e24-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="27e24-108">FindAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-108">FindAssembly Method</span></span>](imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="27e24-109">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="27e24-109">This method is not implemented.</span></span> <span data-ttu-id="27e24-110">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-110">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="27e24-111">FindAssemblyModule 메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-111">FindAssemblyModule Method</span></span>](imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="27e24-112">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="27e24-112">This method is not implemented.</span></span> <span data-ttu-id="27e24-113">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-113">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="27e24-114">GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-114">GetCORSystemDirectory Method</span></span>](imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="27e24-115">현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-115">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="27e24-116">이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-116">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="27e24-117">다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-117">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="27e24-118">GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-118">GetOption Method</span></span>](imetadatadispenserex-getoption-method.md)|<span data-ttu-id="27e24-119">현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-119">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="27e24-120">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-120">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="27e24-121">OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-121">OpenScopeOnITypeInfo Method</span></span>](imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="27e24-122">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="27e24-122">This method is not implemented.</span></span> <span data-ttu-id="27e24-123">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-123">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="27e24-124">SetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="27e24-124">SetOption Method</span></span>](imetadatadispenserex-setoption-method.md)|<span data-ttu-id="27e24-125">지정 된 옵션을 현재 메타 데이터 범위의 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-125">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="27e24-126">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-126">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27e24-127">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27e24-127">Requirements</span></span>  

 <span data-ttu-id="27e24-128">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="27e24-128">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27e24-129">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="27e24-129">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27e24-130">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27e24-130">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27e24-131">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27e24-131">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27e24-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27e24-132">See also</span></span>

- [<span data-ttu-id="27e24-133">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27e24-133">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="27e24-134">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27e24-134">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
- [<span data-ttu-id="27e24-135">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27e24-135">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="27e24-136">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27e24-136">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
