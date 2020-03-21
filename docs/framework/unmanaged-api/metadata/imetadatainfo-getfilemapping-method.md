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
ms.openlocfilehash: 0f5bdf97132c05e765cd6fa423a19bb996105d28
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175267"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="72dd0-102">IMetaDataInfo::GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="72dd0-102">IMetaDataInfo::GetFileMapping Method</span></span>
<span data-ttu-id="72dd0-103">매핑된 파일의 메모리 영역과 매핑 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-103">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="72dd0-104">구문</span><span class="sxs-lookup"><span data-stu-id="72dd0-104">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="72dd0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="72dd0-105">Parameters</span></span>  
 `ppvData`  
 <span data-ttu-id="72dd0-106">【아웃】 매핑된 파일의 시작 부분에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-106">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="72dd0-107">【아웃】 매핑된 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-107">[out] The size of the mapped region.</span></span> <span data-ttu-id="72dd0-108">`fmFlat`이 경우 `pdwMappingType` 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-108">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="72dd0-109">【아웃】 매핑 유형을 나타내는 [CorFile매핑](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-109">[out] A [CorFileMapping](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="72dd0-110">공통 언어 런타임(CLR)의 현재 구현은 항상 반환됩니다. `fmFlat`</span><span class="sxs-lookup"><span data-stu-id="72dd0-110">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="72dd0-111">다른 값은 나중에 사용할 수 있도록 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-111">Other values are reserved for future use.</span></span> <span data-ttu-id="72dd0-112">그러나 이후 버전 이나 서비스 릴리스에서 다른 값을 사용할 수 있으므로 항상 반환 된 값을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-112">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="72dd0-113">Return Value</span><span class="sxs-lookup"><span data-stu-id="72dd0-113">Return Value</span></span>  
  
|<span data-ttu-id="72dd0-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="72dd0-114">HRESULT</span></span>|<span data-ttu-id="72dd0-115">Description</span><span class="sxs-lookup"><span data-stu-id="72dd0-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="72dd0-116">모든 출력이 채워져 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-116">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="72dd0-117">NULL이 인수 값으로 전달되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-117">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="72dd0-118">CLR 구현은 메모리 영역에 대한 정보를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-118">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="72dd0-119">이 문제는 다음과 같은 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-119">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="72dd0-120">- `ofWrite` 또는 `ofCopyMemory` 플래그로 메타데이터 범위가 열렸습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-120">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="72dd0-121">- `ofReadOnly` 메타데이터 범위가 플래그 없이 열렸습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-121">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="72dd0-122">- [IMetaData디스펜서::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타데이터 부분만 여는 데 사용되었습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-122">-   The [IMetaDataDispenser::OpenScopeOnMemory](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="72dd0-123">- 파일이 휴대용 실행 파일 (PE) 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-123">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="72dd0-124">**참고:**  이러한 조건은 CLR 구현에 따라 다르며 이후 버전의 CLR에서 약화될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-124">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="72dd0-125">설명</span><span class="sxs-lookup"><span data-stu-id="72dd0-125">Remarks</span></span>  
 <span data-ttu-id="72dd0-126">`ppvData` 가리키는 메모리는 기본 메타데이터 범위가 열려 있는 경우에만 유효합니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-126">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="72dd0-127">이 메서드가 작동하려면 [IMetaDataScopeer::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) 메서드를 호출하여 디스크 온 파일의 메타데이터를 메모리에 매핑할 `ofReadOnly` 때 플래그를 지정해야 `ofCopyMemory` 하며 또는 플래그를 `ofWrite` 지정해서는 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-127">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="72dd0-128">각 범위에 대한 파일 매핑 형식의 선택은 CLR의 지정된 구현에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-128">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="72dd0-129">사용자가 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-129">It cannot be set by the user.</span></span> <span data-ttu-id="72dd0-130">CLR의 현재 구현은 `fmFlat` 항상 `pdwMappingType`에서 반환되지만 CLR의 이후 버전 또는 지정된 버전의 이후 서비스 릴리스에서 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-130">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="72dd0-131">다른 형식마다 레이아웃과 `pdwMappingType`오프셋이 다르므로 항상 에서 반환된 값을 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-131">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="72dd0-132">세 매개 변수 중 어느 것에 대해서도 NULL을 전달하는 것은 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-132">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="72dd0-133">메서드가 `E_INVALIDARG`반환되고 출력이 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-133">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="72dd0-134">매핑 유형이나 영역 크기를 무시하면 비정상적인 프로그램 종료가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="72dd0-134">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="72dd0-135">요구 사항</span><span class="sxs-lookup"><span data-stu-id="72dd0-135">Requirements</span></span>  
 <span data-ttu-id="72dd0-136">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="72dd0-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="72dd0-137">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="72dd0-137">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="72dd0-138">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="72dd0-138">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="72dd0-139">**.NET Framework 버전:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="72dd0-139">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="72dd0-140">참고 항목</span><span class="sxs-lookup"><span data-stu-id="72dd0-140">See also</span></span>

- [<span data-ttu-id="72dd0-141">IMetaDataInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="72dd0-141">IMetaDataInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatainfo-interface.md)
- [<span data-ttu-id="72dd0-142">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="72dd0-142">CorFileMapping Enumeration</span></span>](../../../../docs/framework/unmanaged-api/metadata/corfilemapping-enumeration.md)
