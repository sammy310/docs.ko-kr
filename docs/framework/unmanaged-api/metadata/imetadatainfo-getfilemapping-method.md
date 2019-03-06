---
title: IMetaDataInfo::GetFileMapping 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataInfo.GetFileMapping
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataInfo::GetFileMapping
helpviewer_keywords:
- IMetaDataInfo::GetFileMapping method [.NET Framework metadata]
- GetFileMapping method [.NET Framework metadata]
ms.assetid: 2868dfec-c992-4606-88bb-a8e0b6b18271
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b45d78548f2b1a7e17f61c5228cd68f228fe4980
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57478861"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="9a72e-102">IMetaDataInfo::GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="9a72e-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="9a72e-103">매핑의 형식과 매핑된 파일의 메모리 영역을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9a72e-104">구문</span><span class="sxs-lookup"><span data-stu-id="9a72e-104">Syntax</span></span>  
  
```  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9a72e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9a72e-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="9a72e-106">[out] 매핑된 파일의 시작 부분에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="9a72e-107">[out] 매핑된 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="9a72e-108">하는 경우 `pdwMappingType` 는 `fmFlat`, 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="9a72e-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) 매핑 형식을 나타내는 값입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="9a72e-110">CLR (공용 언어 런타임)의 현재 구현은 항상 `fmFlat`합니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="9a72e-111">다른 값은 나중에 사용에 대 한 예약 됩니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-111">Other values are reserved for future use.</span></span> <span data-ttu-id="9a72e-112">그러나 항상 확인 해야 반환된 된 값이 다른 값 이후 버전에서 사용할 수 있습니다 하거나 서비스 릴리스 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9a72e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="9a72e-113">Return Value</span></span>  
  
|<span data-ttu-id="9a72e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9a72e-114">HRESULT</span></span>|<span data-ttu-id="9a72e-115">설명</span><span class="sxs-lookup"><span data-stu-id="9a72e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9a72e-116">모든 출력은 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="9a72e-117">NULL 인수 값으로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="9a72e-118">CLR 구현은 메모리 영역에 대 한 정보를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="9a72e-119">이 작업은 다음과 같은 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="9a72e-120">-메타 데이터 범위를 사용 하 여 열린 합니다 `ofWrite` 또는 `ofCopyMemory` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="9a72e-121">하지 않고 열림-메타 데이터 범위는 `ofReadOnly` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="9a72e-122">- [Imetadatadispenser:: Openscopeonmemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타 데이터 부분에 여는 데 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="9a72e-123">-파일이 pe (이식 가능) 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="9a72e-124">**참고:**  이러한 조건을 CLR 구현에 종속 되며 기능이 약화 될 수 이후 버전의 CLR.</span><span class="sxs-lookup"><span data-stu-id="9a72e-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9a72e-125">설명</span><span class="sxs-lookup"><span data-stu-id="9a72e-125">Remarks</span></span>  
 <span data-ttu-id="9a72e-126">메모리는 `ppvData` 동안만 기본 메타 데이터 범위의 열려 가리키는 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="9a72e-127">이 메서드를 호출 하 여 메모리에는 디스크에 있는 파일의 메타 데이터를 매핑할 때는 작동 되려면 합니다 [imetadatadispenser:: Openscope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 지정 해야 합니다는 `ofReadOnly` 플래그를 지정 해야 합니다는 `ofWrite` 또는 `ofCopyMemory` 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="9a72e-128">선택한 각 범위에 대 한 파일 매핑 형식은 CLR의 특정된 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="9a72e-129">사용자가 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-129">It cannot be set by the user.</span></span> <span data-ttu-id="9a72e-130">CLR의 현재 구현은 항상 `fmFlat` 에서 `pdwMappingType`, CLR의 버전 또는 나중에 지정된 된 버전의 서비스 릴리스에서도 나중에 변경할 수 있습니다이 있지만.</span><span class="sxs-lookup"><span data-stu-id="9a72e-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="9a72e-131">반환된 된 값을 항상 확인 해야 `pdwMappingType`이므로 다양 한 레이아웃 및 오프셋 다른 형식을 갖습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="9a72e-132">세 가지 매개 변수 중 하나는 NULL을 전달 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="9a72e-133">메서드는 반환 `E_INVALIDARG`, 출력 하나도 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="9a72e-134">매핑 형식 또는 영역의 크기를 무시 하 고 비정상적인 프로그램 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9a72e-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9a72e-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9a72e-135">Requirements</span></span>  
 <span data-ttu-id="9a72e-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="9a72e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9a72e-137">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9a72e-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9a72e-138">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="9a72e-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9a72e-139">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9a72e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9a72e-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="9a72e-140">See also</span></span>
- [<span data-ttu-id="9a72e-141">IMetaDataInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9a72e-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="9a72e-142">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="9a72e-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
