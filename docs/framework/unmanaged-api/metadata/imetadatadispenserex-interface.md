---
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
ms.openlocfilehash: 985cdea670714394119fb846e9e55a01713559a9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431150"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="4b27b-102">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b27b-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="4b27b-103">[IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) 인터페이스를 확장 하 여 메타 데이터 api가 현재 메타 데이터 범위에서 작동 하는 방식을 제어할 수 있는 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4b27b-104">메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-104">Methods</span></span>  
  
|<span data-ttu-id="4b27b-105">메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-105">Method</span></span>|<span data-ttu-id="4b27b-106">설명</span><span class="sxs-lookup"><span data-stu-id="4b27b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4b27b-107">FindAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="4b27b-108">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-108">This method is not implemented.</span></span> <span data-ttu-id="4b27b-109">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="4b27b-110">FindAssemblyModule 메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="4b27b-111">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-111">This method is not implemented.</span></span> <span data-ttu-id="4b27b-112">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="4b27b-113">GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="4b27b-114">현재 CLR (공용 언어 런타임)을 보유 하 고 있는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="4b27b-115">이 메서드는 in-process 디버거가 사용할 때만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="4b27b-116">다른 구성 요소에서 호출 되는 경우 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="4b27b-117">GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="4b27b-118">현재 메타 데이터 범위에 지정 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="4b27b-119">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="4b27b-120">OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="4b27b-121">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-121">This method is not implemented.</span></span> <span data-ttu-id="4b27b-122">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="4b27b-123">SetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="4b27b-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="4b27b-124">지정 된 옵션을 현재 메타 데이터 범위의 지정 된 값으로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="4b27b-125">옵션은 현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 합니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4b27b-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4b27b-126">Requirements</span></span>  
 <span data-ttu-id="4b27b-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="4b27b-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b27b-128">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4b27b-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b27b-129">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4b27b-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b27b-130">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b27b-130">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b27b-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4b27b-131">See also</span></span>

- [<span data-ttu-id="4b27b-132">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b27b-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="4b27b-133">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b27b-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="4b27b-134">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b27b-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="4b27b-135">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4b27b-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
