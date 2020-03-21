---
title: IMetaDataDispenser::DefineScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.DefineScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::DefineScope
helpviewer_keywords:
- DefineScope method [.NET Framework metadata]
- IMetaDataDispenser::DefineScope method [.NET Framework metadata]
ms.assetid: af28db02-29af-45ac-aec6-8d6c6123c2ff
topic_type:
- apiref
ms.openlocfilehash: 2f9325f3795262a0c33af02f87fc5d3a020658cf
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177649"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="c9cc2-102">IMetaDataDispenser::DefineScope 메서드</span><span class="sxs-lookup"><span data-stu-id="c9cc2-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="c9cc2-103">메모리에 새 메타데이터를 만들 수 있는 새 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9cc2-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9cc2-104">Syntax</span></span>  
  
```cpp  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9cc2-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c9cc2-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="c9cc2-106">【인】 만들 메타데이터 구조의 CLSID입니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="c9cc2-107">.NET Framework 버전 2.0의 경우 이 값을 CLSID_CorMetaDataRuntime.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="c9cc2-108">【인】 옵션을 지정하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-108">[in] Flags that specify options.</span></span> <span data-ttu-id="c9cc2-109">.NET Framework 2.0의 경우 이 값은 0이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="c9cc2-110">【인】 반송할 원하는 메타데이터 인터페이스의 IID; 호출자는 인터페이스를 사용하여 새 메타데이터를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="c9cc2-111">값은 `riid` "내각" 인터페이스 중 하나를 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="c9cc2-112">유효한 값은 IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit 또는 IID_IMetaDataEmit2.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="c9cc2-113">【아웃】 반환된 인터페이스에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c9cc2-114">설명</span><span class="sxs-lookup"><span data-stu-id="c9cc2-114">Remarks</span></span>  
 <span data-ttu-id="c9cc2-115">`DefineScope`메모리 내 메타데이터 테이블 집합을 만들고, 메타데이터에 대한 고유한 GUID(모듈 버전 식별자 또는 MVID)를 생성하고, 내보내지는 컴파일 유닛에 대한 모듈 테이블에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-115">`DefineScope` creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="c9cc2-116">적절 하 게 [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) 또는 [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) 메서드를 사용 하 여 메타 데이터 범위에 특성을 연결 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9cc2-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9cc2-117">Requirements</span></span>  
 <span data-ttu-id="c9cc2-118">**플랫폼:** [시스템 요구 사항을](../../../../docs/framework/get-started/system-requirements.md)참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="c9cc2-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c9cc2-119">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="c9cc2-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c9cc2-120">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c9cc2-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c9cc2-121">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c9cc2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9cc2-122">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c9cc2-122">See also</span></span>

- [<span data-ttu-id="c9cc2-123">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9cc2-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="c9cc2-124">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9cc2-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="c9cc2-125">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9cc2-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="c9cc2-126">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9cc2-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="c9cc2-127">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9cc2-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
