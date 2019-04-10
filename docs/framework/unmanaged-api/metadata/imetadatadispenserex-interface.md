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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 96475086b1244ae75ed692dd10cb693af0be9af7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59186955"
---
# <a name="imetadatadispenserex-interface"></a><span data-ttu-id="b1181-102">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1181-102">IMetaDataDispenserEx Interface</span></span>
<span data-ttu-id="b1181-103">확장 된 [IMetaDataDispenser 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) 메타 데이터 Api는 현재 메타 데이터 범위에서 작동 하는 방법을 제어 하는 기능을 제공 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-103">Extends the [IMetaDataDispenser Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md) interface to provide the capability to control how the metadata APIs operate on the current metadata scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="b1181-104">메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-104">Methods</span></span>  
  
|<span data-ttu-id="b1181-105">메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-105">Method</span></span>|<span data-ttu-id="b1181-106">설명</span><span class="sxs-lookup"><span data-stu-id="b1181-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="b1181-107">FindAssembly 메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-107">FindAssembly Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassembly-method.md)|<span data-ttu-id="b1181-108">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-108">This method is not implemented.</span></span> <span data-ttu-id="b1181-109">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-109">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b1181-110">FindAssemblyModule 메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-110">FindAssemblyModule Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-findassemblymodule-method.md)|<span data-ttu-id="b1181-111">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-111">This method is not implemented.</span></span> <span data-ttu-id="b1181-112">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-112">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b1181-113">GetCORSystemDirectory 메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-113">GetCORSystemDirectory Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getcorsystemdirectory-method.md)|<span data-ttu-id="b1181-114">현재 CLR (공용 언어 런타임) 저장 하는 디렉터리를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-114">Gets the directory that holds the current common language runtime (CLR).</span></span> <span data-ttu-id="b1181-115">이 메서드는 out-of-process-디버거에서 사용에 대해서만 지원 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-115">This method is supported only for use by out-of-process debuggers.</span></span> <span data-ttu-id="b1181-116">다른 구성 요소에서 호출 하는 경우 E_NOTIMPL이 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-116">If called from another component, it will return E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b1181-117">GetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-117">GetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-getoption-method.md)|<span data-ttu-id="b1181-118">현재 메타 데이터 범위에 대 한 지정된 된 옵션의 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-118">Gets the value of the specified option for the current metadata scope.</span></span> <span data-ttu-id="b1181-119">현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-119">The option controls how calls to the current metadata scope are handled.</span></span>|  
|[<span data-ttu-id="b1181-120">OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-120">OpenScopeOnITypeInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-openscopeonitypeinfo-method.md)|<span data-ttu-id="b1181-121">이 메서드가 구현되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-121">This method is not implemented.</span></span> <span data-ttu-id="b1181-122">를 호출 하는 경우 E_NOTIMPL을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-122">If called, it returns E_NOTIMPL.</span></span>|  
|[<span data-ttu-id="b1181-123">SetOption 메서드</span><span class="sxs-lookup"><span data-stu-id="b1181-123">SetOption Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md)|<span data-ttu-id="b1181-124">현재 메타 데이터 범위에 대 한 지정 된 값으로 지정된 된 옵션을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-124">Sets the specified option to a given value for the current metadata scope.</span></span> <span data-ttu-id="b1181-125">현재 메타 데이터 범위에 대 한 호출을 처리 하는 방법을 제어 하는 옵션입니다.</span><span class="sxs-lookup"><span data-stu-id="b1181-125">The option controls how calls to the current metadata scope are handled.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b1181-126">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b1181-126">Requirements</span></span>  
 <span data-ttu-id="b1181-127">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="b1181-127">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b1181-128">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="b1181-128">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b1181-129">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="b1181-129">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="b1181-130">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="b1181-130">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="b1181-131">참고자료</span><span class="sxs-lookup"><span data-stu-id="b1181-131">See also</span></span>

- [<span data-ttu-id="b1181-132">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1181-132">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="b1181-133">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1181-133">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="b1181-134">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1181-134">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="b1181-135">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b1181-135">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
