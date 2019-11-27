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
ms.openlocfilehash: 0cd2071d4410615a08e774ba30e0e8fe8d1fa7c7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436181"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="f462e-102">IMetaDataInfo::GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="f462e-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="f462e-103">매핑된 파일의 메모리 영역 및 매핑 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f462e-104">구문</span><span class="sxs-lookup"><span data-stu-id="f462e-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,   
    [out] ULONGLONG            *pcbData,   
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f462e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f462e-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="f462e-106">제한이 매핑된 파일의 시작에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="f462e-107">제한이 매핑된 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="f462e-108">`pdwMappingType` `fmFlat`경우 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="f462e-109">제한이 매핑의 유형을 나타내는 [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="f462e-110">CLR (공용 언어 런타임)의 현재 구현은 항상 `fmFlat`을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="f462e-111">다른 값은 나중에 사용할 수 있도록 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-111">Other values are reserved for future use.</span></span> <span data-ttu-id="f462e-112">그러나 이후 버전 또는 서비스 릴리스에서 다른 값을 사용할 수 있기 때문에 항상 반환 된 값을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f462e-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="f462e-113">Return Value</span></span>  
  
|<span data-ttu-id="f462e-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f462e-114">HRESULT</span></span>|<span data-ttu-id="f462e-115">설명</span><span class="sxs-lookup"><span data-stu-id="f462e-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f462e-116">모든 출력이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="f462e-117">NULL이 인수 값으로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="f462e-118">CLR 구현은 메모리 영역에 대 한 정보를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="f462e-119">이 문제는 다음과 같은 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="f462e-120">-`ofWrite` 또는 `ofCopyMemory` 플래그를 사용 하 여 메타 데이터 범위를 열었습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="f462e-121">-메타 데이터 범위가 `ofReadOnly` 플래그 없이 열렸습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="f462e-122">- [IMetaDataDispenser:: OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타 데이터 부분만 여는 데 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="f462e-123">-파일이 PE (이식 가능한 실행 파일) 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="f462e-124">**참고:**  이러한 조건은 CLR 구현에 따라 달라 지 며 CLR의 이후 버전에서 약화 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f462e-125">설명</span><span class="sxs-lookup"><span data-stu-id="f462e-125">Remarks</span></span>  
 <span data-ttu-id="f462e-126">`ppvData` 가리키는 메모리는 기본 메타 데이터 범위가 열려 있는 동안에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="f462e-127">이 메서드가 작동 하려면 [IMetaDataDispenser:: OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 메서드를 호출 하 여 디스크에 있는 파일의 메타 데이터를 메모리에 매핑하면 `ofReadOnly` 플래그를 지정 해야 하며 `ofWrite` 또는 `ofCopyMemory` 플래그를 지정 하지 않아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="f462e-128">각 범위에 대 한 파일 매핑 형식의 선택은 CLR의 지정 된 구현과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="f462e-129">사용자가 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-129">It cannot be set by the user.</span></span> <span data-ttu-id="f462e-130">CLR의 현재 구현은 항상 `pdwMappingType`에 `fmFlat`를 반환 하지만이는 이후 버전의 CLR 또는 지정 된 버전의 이후 서비스 릴리스에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="f462e-131">서로 다른 레이아웃과 오프셋이 있으므로 항상 `pdwMappingType`에서 반환 된 값을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="f462e-132">세 매개 변수 중 하나에 대해 NULL을 전달 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="f462e-133">메서드는 `E_INVALIDARG`을 반환 하 고 출력은 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="f462e-134">매핑 형식이 나 영역의 크기를 무시 하면 비정상적인 프로그램이 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f462e-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f462e-135">Requirements</span></span>  
 <span data-ttu-id="f462e-136">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f462e-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f462e-137">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="f462e-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f462e-138">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f462e-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f462e-139">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f462e-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f462e-140">참고자료</span><span class="sxs-lookup"><span data-stu-id="f462e-140">See also</span></span>

- [<span data-ttu-id="f462e-141">IMetaDataInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f462e-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="f462e-142">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="f462e-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
