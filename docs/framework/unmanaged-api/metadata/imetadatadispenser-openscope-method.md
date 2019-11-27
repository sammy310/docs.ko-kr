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
ms.openlocfilehash: 5ce1af82631531f8f7105fbf92ba78db3cca437b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74442321"
---
# <a name="imetadatadispenseropenscope-method"></a><span data-ttu-id="09eec-102">IMetaDataDispenser::OpenScope 메서드</span><span class="sxs-lookup"><span data-stu-id="09eec-102">IMetaDataDispenser::OpenScope Method</span></span>
<span data-ttu-id="09eec-103">기존 디스크에 있는 기존 파일을 열고 해당 메타 데이터를 메모리에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-103">Opens an existing, on-disk file and maps its metadata into memory.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09eec-104">구문</span><span class="sxs-lookup"><span data-stu-id="09eec-104">Syntax</span></span>  
  
```cpp  
HRESULT OpenScope (  
    [in]  LPCWSTR     szScope,   
    [in]  DWORD       dwOpenFlags,   
    [in]  REFIID      riid,   
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="09eec-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="09eec-105">Parameters</span></span>  
 `szScope`  
 <span data-ttu-id="09eec-106">진행 열 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-106">[in] The name of the file to be opened.</span></span> <span data-ttu-id="09eec-107">이 파일은 CLR (공용 언어 런타임) 메타 데이터를 포함 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-107">The file must contain common language runtime (CLR) metadata.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="09eec-108">진행 열기에 대 한 모드 (읽기, 쓰기 등)를 지정 하는 [Coropenflags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-108">[in] A value of the [CorOpenFlags](../../../../docs/framework/unmanaged-api/metadata/coropenflags-enumeration.md) enumeration to specify the mode (read, write, and so on) for opening.</span></span>  
  
 `riid`  
 <span data-ttu-id="09eec-109">진행 반환할 원하는 메타 데이터 인터페이스의 IID입니다. 호출자는 인터페이스를 사용 하 여 메타 데이터를 가져오거나 (읽기) 내보내기 (쓰기) 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-109">[in] The IID of the desired metadata interface to be returned; the caller will use the interface to import (read) or emit (write) metadata.</span></span>  
  
 <span data-ttu-id="09eec-110">`riid` 값은 "가져오기" 또는 "내보내기" 인터페이스 중 하나를 지정 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-110">The value of `riid` must specify one of the "import" or "emit" interfaces.</span></span> <span data-ttu-id="09eec-111">유효한 값은 IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2 또는 IID_IMetaDataImport2입니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-111">Valid values are IID_IMetaDataEmit, IID_IMetaDataImport, IID_IMetaDataAssemblyEmit, IID_IMetaDataAssemblyImport, IID_IMetaDataEmit2, or IID_IMetaDataImport2.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="09eec-112">제한이 반환 된 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-112">[out] The pointer to the returned interface.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="09eec-113">설명</span><span class="sxs-lookup"><span data-stu-id="09eec-113">Remarks</span></span>  
 <span data-ttu-id="09eec-114">메타 데이터의 메모리 내 복사본은 "가져오기" 인터페이스 중 하나에서 메서드를 사용 하 여 쿼리하거나 "내보내기" 인터페이스 중 하나에서 메서드를 사용 하 여 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-114">The in-memory copy of the metadata can be queried using methods from one of the "import" interfaces, or added to using methods from the one of the "emit" interfaces.</span></span>  
  
 <span data-ttu-id="09eec-115">대상 파일에 CLR 메타 데이터가 없는 경우에는 `OpenScope` 메서드가 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-115">If the target file does not contain CLR metadata, the `OpenScope` method will fail.</span></span>  
  
 <span data-ttu-id="09eec-116">.NET Framework 버전 1.0 및 버전 1.1에서 `dwOpenFlags` ofRead로 설정 된 범위를 열면 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-116">In the .NET Framework version 1.0 and version 1.1, if a scope is opened with `dwOpenFlags` set to ofRead, it is eligible for sharing.</span></span> <span data-ttu-id="09eec-117">즉, `OpenScope`에 대 한 후속 호출에서 이전에 연 파일의 이름을 전달 하는 경우 기존 범위가 다시 사용 되 고 새 데이터 구조 집합이 생성 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-117">That is, if subsequent calls to `OpenScope` pass in the name of a file that was previously opened, the existing scope is reused and a new set of data structures is not created.</span></span> <span data-ttu-id="09eec-118">그러나 이러한 공유로 인해 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-118">However, problems can arise due to this sharing.</span></span>  
  
 <span data-ttu-id="09eec-119">.NET Framework 버전 2.0에서는 ofRead로 설정 된 `dwOpenFlags`으로 열린 범위가 더 이상 공유 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-119">In the .NET Framework version 2.0, scopes opened with `dwOpenFlags` set to ofRead are no longer shared.</span></span> <span data-ttu-id="09eec-120">OfReadOnly 값을 사용 하 여 범위를 공유할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-120">Use the ofReadOnly value to allow the scope to be shared.</span></span> <span data-ttu-id="09eec-121">범위가 공유 되 면 "읽기/쓰기" 메타 데이터 인터페이스를 사용 하는 쿼리는 실패 합니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-121">When a scope is shared, queries that use "read/write" metadata interfaces will fail.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="09eec-122">요구 사항</span><span class="sxs-lookup"><span data-stu-id="09eec-122">Requirements</span></span>  
 <span data-ttu-id="09eec-123">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="09eec-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09eec-124">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="09eec-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="09eec-125">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="09eec-125">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="09eec-126">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09eec-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09eec-127">참고자료</span><span class="sxs-lookup"><span data-stu-id="09eec-127">See also</span></span>

- [<span data-ttu-id="09eec-128">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-128">IMetaDataDispenser Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
- [<span data-ttu-id="09eec-129">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-129">IMetaDataDispenserEx Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)
- [<span data-ttu-id="09eec-130">IMetaDataAssemblyEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-130">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)
- [<span data-ttu-id="09eec-131">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-131">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
- [<span data-ttu-id="09eec-132">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-132">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="09eec-133">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-133">IMetaDataEmit2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
- [<span data-ttu-id="09eec-134">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-134">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="09eec-135">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="09eec-135">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
