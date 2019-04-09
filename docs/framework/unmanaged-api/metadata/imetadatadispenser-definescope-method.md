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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 76a439effad9cb3f6dcdd232590cf2196ee7ab99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59101408"
---
# <a name="imetadatadispenserdefinescope-method"></a><span data-ttu-id="59b24-102">IMetaDataDispenser::DefineScope 메서드</span><span class="sxs-lookup"><span data-stu-id="59b24-102">IMetaDataDispenser::DefineScope Method</span></span>
<span data-ttu-id="59b24-103">새 메타 데이터를 만들 수 있는 메모리에 새 영역을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-103">Creates a new area in memory in which you can create new metadata.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="59b24-104">구문</span><span class="sxs-lookup"><span data-stu-id="59b24-104">Syntax</span></span>  
  
```  
HRESULT DefineScope (  
    [in]  REFCLSID    rclsid,  
    [in]  DWORD       dwCreateFlags,  
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="59b24-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="59b24-105">Parameters</span></span>  
 `rclsid`  
 <span data-ttu-id="59b24-106">[in] 만들 메타 데이터 구조 버전의 CLSID입니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-106">[in] The CLSID of the version of metadata structures to be created.</span></span> <span data-ttu-id="59b24-107">이 값은.NET Framework 버전 2.0에 대 한 CLSID_CorMetaDataRuntime 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-107">This value must be CLSID_CorMetaDataRuntime for the .NET Framework version 2.0.</span></span>  
  
 `dwCreateFlags`  
 <span data-ttu-id="59b24-108">[in] 옵션을 지정 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-108">[in] Flags that specify options.</span></span> <span data-ttu-id="59b24-109">이 값에는.NET Framework 2.0에 대 한 0 이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-109">This value must be zero for the .NET Framework 2.0.</span></span>  
  
 `riid`  
 <span data-ttu-id="59b24-110">[in] 반환 될 원하는 메타 데이터 인터페이스의 IID 호출자에 게 새 메타 데이터를 만드는 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-110">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to create the new metadata.</span></span>  
  
 <span data-ttu-id="59b24-111">변수의 `riid` "내보내기" 인터페이스 중 하나를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-111">The value of `riid` must specify one of the "emit" interfaces.</span></span> <span data-ttu-id="59b24-112">유효한 값은 IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, 또는 IID_IMetaDataEmit2입니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-112">Valid values are IID_IMetaDataEmit, IID_IMetaDataAssemblyEmit, or IID_IMetaDataEmit2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="59b24-113">[out] 반환 되는 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-113">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="59b24-114">설명</span><span class="sxs-lookup"><span data-stu-id="59b24-114">Remarks</span></span>  
 `DefineScope` <span data-ttu-id="59b24-115">메모리 내 메타 데이터 테이블 집합을 만듭니다, 그리고 메타 데이터에 대 한 고유 GUID (모듈 버전 식별자, 또는 MVID) 생성 및 내보낼 컴파일 단위에 대 한 모듈 테이블에 항목을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-115">creates a set of in-memory metadata tables, generates a unique GUID (module version identifier, or MVID) for the metadata, and creates an entry in the module table for the compilation unit being emitted.</span></span>  
  
 <span data-ttu-id="59b24-116">사용 하 여 전체 특성 메타 데이터 범위에 연결할 수는 [imetadataemit:: Setmoduleprops](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) 하거나 [imetadataemit:: Definecustomattribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) 메서드를 적절 하 게 합니다.</span><span class="sxs-lookup"><span data-stu-id="59b24-116">You can attach attributes to the metadata scope as a whole by using the [IMetaDataEmit::SetModuleProps](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setmoduleprops-method.md) or [IMetaDataEmit::DefineCustomAttribute](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-definecustomattribute-method.md) method, as appropriate.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="59b24-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="59b24-117">Requirements</span></span>  
 <span data-ttu-id="59b24-118">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="59b24-118">**Platform:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="59b24-119">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="59b24-119">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="59b24-120">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="59b24-120">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="59b24-121">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="59b24-121">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="59b24-122">참고자료</span><span class="sxs-lookup"><span data-stu-id="59b24-122">See also</span></span>

- [<span data-ttu-id="59b24-123">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b24-123">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="59b24-124">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b24-124">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="59b24-125">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b24-125">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="59b24-126">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b24-126">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="59b24-127">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="59b24-127">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
