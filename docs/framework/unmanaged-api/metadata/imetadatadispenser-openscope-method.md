---
title: IMetaDataDispenser::OpenScope 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenser.OpenScope
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenser::OpenScope
helpviewer_keywords:
- IMetaDataDispenser::OpenScope method [.NET Framework metadata]
- OpenScope method, IMetaDataDispenser interface [.NET Framework metadata]
ms.assetid: 65063ad5-e0d9-4c01-8f8b-9a5950109fa6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5b94987631f7dbbe39e585a8ea2c2252b9427613
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59079606"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="13a9f-102">IMetaDataDispenser::OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="13a9f-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="13a9f-103">기존의 디스크에 파일을 열고 해당 메타 데이터를 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13a9f-104">구문</span><span class="sxs-lookup"><span data-stu-id="13a9f-104">Syntax</span></span>  
  
```  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="13a9f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="13a9f-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="13a9f-106">[in] 열려는 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="13a9f-107">파일에는 공용 언어 런타임 (CLR) 메타 데이터가 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="13a9f-108">[in] 값을 [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열기 위한 모드 (읽기, 쓰기 및 등)를 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="13a9f-109">[in] 반환 될 원하는 메타 데이터 인터페이스의 IID 호출자에 게 가져오기 (읽기) 또는 (쓰기) 메타 데이터 내보내기 인터페이스를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="13a9f-110">변수의 `riid` "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="13a9f-111">유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, 또는 IID_IMetaDataImport2입니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="13a9f-112">[out] 반환 되는 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="13a9f-113">설명</span><span class="sxs-lookup"><span data-stu-id="13a9f-113">Remarks</span></span>  
 <span data-ttu-id="13a9f-114">"가져오기" 인터페이스 중 하나에서 메서드를 사용 하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 메타 데이터의 메모리 내 복사본을 쿼리할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="13a9f-115">CLR 메타 데이터를 대상 파일에 없으면는 `OpenScope` 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="13a9f-116">.NET Framework 버전 1.0 및 1.1 경우 범위는으로 열고 `dwOpenFlags` ofRead로 설정한 것이 공유에 적합 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="13a9f-117">즉, 후속 경우 호출 `OpenScope` 이전에 연 파일의 이름을 전달, 기존 범위를 다시 사용 되 고 새 데이터 구조 집합이 만들어지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="13a9f-118">그러나 이러한 공유로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="13a9f-119">.NET framework 버전 2.0에서 범위 사용 하 여 연 `dwOpenFlags` ofRead로 더 이상 공유 됩니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="13a9f-120">범위를 공유할 수 있도록 ofReadOnly 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="13a9f-121">범위를 공유 하면 "읽기/쓰기" 메타 데이터 인터페이스를 사용 하는 쿼리가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="13a9f-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13a9f-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13a9f-122">Requirements</span></span>  
 <span data-ttu-id="13a9f-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="13a9f-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13a9f-124">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="13a9f-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13a9f-125">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="13a9f-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13a9f-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13a9f-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13a9f-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="13a9f-127">See also</span></span>

- [<span data-ttu-id="13a9f-128">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="13a9f-129">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="13a9f-130">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="13a9f-131">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="13a9f-132">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="13a9f-133">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="13a9f-134">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="13a9f-135">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13a9f-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
