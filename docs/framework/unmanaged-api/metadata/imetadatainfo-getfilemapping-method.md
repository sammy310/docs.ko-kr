---
description: '자세히 알아보기: IMetaDataInfo:: GetFileMapping 메서드'
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
ms.openlocfilehash: 82a1a23c50a4d8340804f66966933fc6a11e0f8c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688483"
---
# <a name="imetadatainfogetfilemapping-method"></a><span data-ttu-id="b9534-103">IMetaDataInfo::GetFileMapping 메서드</span><span class="sxs-lookup"><span data-stu-id="b9534-103">IMetaDataInfo::GetFileMapping Method</span></span>

<span data-ttu-id="b9534-104">매핑된 파일의 메모리 영역 및 매핑 유형을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-104">Gets the memory region of the mapped file, and the type of mapping.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b9534-105">구문</span><span class="sxs-lookup"><span data-stu-id="b9534-105">Syntax</span></span>  
  
```cpp  
HRESULT GetFileMapping (  
    [out] const void           **ppvData,
    [out] ULONGLONG            *pcbData,
    [out] DWORD                *pdwMappingType  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b9534-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b9534-106">Parameters</span></span>  

 `ppvData`  
 <span data-ttu-id="b9534-107">제한이 매핑된 파일의 시작에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-107">[out] A pointer to the start of the mapped file.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="b9534-108">제한이 매핑된 영역의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-108">[out] The size of the mapped region.</span></span> <span data-ttu-id="b9534-109">`pdwMappingType`가 이면 `fmFlat` 파일의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-109">If `pdwMappingType` is `fmFlat`, this is the size of the file.</span></span>  
  
 `pdwMappingType`  
 <span data-ttu-id="b9534-110">제한이 매핑의 유형을 나타내는 [CorFileMapping](corfilemapping-enumeration.md) 값입니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-110">[out] A [CorFileMapping](corfilemapping-enumeration.md) value that indicates the type of mapping.</span></span> <span data-ttu-id="b9534-111">CLR (공용 언어 런타임)의 현재 구현은 항상를 반환 `fmFlat` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-111">The current implementation of the common language runtime (CLR) always returns `fmFlat`.</span></span> <span data-ttu-id="b9534-112">다른 값은 나중에 사용할 수 있도록 예약되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-112">Other values are reserved for future use.</span></span> <span data-ttu-id="b9534-113">그러나 이후 버전 또는 서비스 릴리스에서 다른 값을 사용할 수 있기 때문에 항상 반환 된 값을 확인 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-113">However, you should always verify the returned value, because other values may be enabled in future versions or service releases.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b9534-114">Return Value</span><span class="sxs-lookup"><span data-stu-id="b9534-114">Return Value</span></span>  
  
|<span data-ttu-id="b9534-115">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b9534-115">HRESULT</span></span>|<span data-ttu-id="b9534-116">설명</span><span class="sxs-lookup"><span data-stu-id="b9534-116">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="b9534-117">모든 출력이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-117">All outputs are filled.</span></span>|  
|`E_INVALIDARG`|<span data-ttu-id="b9534-118">NULL이 인수 값으로 전달 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-118">NULL was passed as an argument value.</span></span>|  
|`COR_E_NOTSUPPORTED`|<span data-ttu-id="b9534-119">CLR 구현은 메모리 영역에 대 한 정보를 제공할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-119">The CLR implementation cannot provide information about the memory region.</span></span> <span data-ttu-id="b9534-120">이 문제는 다음과 같은 이유로 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-120">This can happen for the following reasons:</span></span><br /><br /> <span data-ttu-id="b9534-121">-메타 데이터 범위가 또는 플래그를 사용 하 여 열렸습니다 `ofWrite` `ofCopyMemory` .</span><span class="sxs-lookup"><span data-stu-id="b9534-121">-   The metadata scope was opened with the `ofWrite` or `ofCopyMemory` flag.</span></span><br /><span data-ttu-id="b9534-122">-메타 데이터 범위가 플래그 없이 열렸습니다 `ofReadOnly` .</span><span class="sxs-lookup"><span data-stu-id="b9534-122">-   The metadata scope was opened without the `ofReadOnly` flag.</span></span><br /><span data-ttu-id="b9534-123">- [IMetaDataDispenser:: OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) 메서드는 파일의 메타 데이터 부분만 여는 데 사용 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-123">-   The [IMetaDataDispenser::OpenScopeOnMemory](imetadatadispenser-openscopeonmemory-method.md) method was used to open only the metadata portion of the file.</span></span><br /><span data-ttu-id="b9534-124">-파일이 PE (이식 가능한 실행 파일) 파일이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-124">-   The file is not a portable executable (PE) file.</span></span> <span data-ttu-id="b9534-125">**참고:**  이러한 조건은 CLR 구현에 따라 달라 지 며 CLR의 이후 버전에서 약화 될 가능성이 높습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-125">**Note:**  These conditions depend on the CLR implementation, and are likely to be weakened in future versions of the CLR.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b9534-126">설명</span><span class="sxs-lookup"><span data-stu-id="b9534-126">Remarks</span></span>  

 <span data-ttu-id="b9534-127">가 가리키는 메모리는 `ppvData` 기본 메타 데이터 범위가 열려 있는 동안에만 유효 합니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-127">The memory that `ppvData` points to is valid only as long as the underlying metadata scope is open.</span></span>  
  
 <span data-ttu-id="b9534-128">이 메서드가 작동 하려면 [IMetaDataDispenser:: OpenScope](imetadatadispenser-openscope-method.md) 메서드를 호출 하 여 디스크에 있는 파일의 메타 데이터를 메모리에 매핑하면 플래그를 지정 해야 `ofReadOnly` 하며 또는 플래그를 지정 하지 않아야 합니다 `ofWrite` `ofCopyMemory` .</span><span class="sxs-lookup"><span data-stu-id="b9534-128">In order for this method to work, when you map the metadata of an on-disk file into memory by calling the [IMetaDataDispenser::OpenScope](imetadatadispenser-openscope-method.md) method, you must specify the `ofReadOnly` flag and you must not specify the `ofWrite` or `ofCopyMemory` flag.</span></span>  
  
 <span data-ttu-id="b9534-129">각 범위에 대 한 파일 매핑 형식의 선택은 CLR의 지정 된 구현과 관련이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-129">The choice of file mapping type for each scope is specific to a given implementation of the CLR.</span></span> <span data-ttu-id="b9534-130">사용자가 설정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-130">It cannot be set by the user.</span></span> <span data-ttu-id="b9534-131">CLR의 현재 구현은 항상 `fmFlat` `pdwMappingType` 를 반환 하지만이는 이후 버전의 clr 또는 지정 된 버전의 이후 서비스 릴리스에서 변경 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-131">The current implementation of the CLR always returns `fmFlat` in `pdwMappingType`, but this can change in future versions of the CLR or in future service releases of a given version.</span></span> <span data-ttu-id="b9534-132">서로 다른 레이아웃과 오프셋이 있으므로 항상에서 반환 된 값을 확인 해야 합니다 `pdwMappingType` .</span><span class="sxs-lookup"><span data-stu-id="b9534-132">You should always check the returned value in `pdwMappingType`, because different types will have different layouts and offsets.</span></span>  
  
 <span data-ttu-id="b9534-133">세 매개 변수 중 하나에 대해 NULL을 전달 하는 것은 지원 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-133">Passing NULL for any of the three parameters is not supported.</span></span> <span data-ttu-id="b9534-134">메서드는 `E_INVALIDARG` 를 반환 하 고 출력은 채워지지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-134">The method returns `E_INVALIDARG`, and none of the outputs are filled.</span></span> <span data-ttu-id="b9534-135">매핑 형식이 나 영역의 크기를 무시 하면 비정상적인 프로그램이 종료 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-135">Ignoring the mapping type or the size of the region can result in abnormal program termination.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b9534-136">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b9534-136">Requirements</span></span>  

 <span data-ttu-id="b9534-137">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b9534-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9534-138">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b9534-138">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b9534-139">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b9534-139">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b9534-140">**.NET Framework 버전:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b9534-140">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9534-141">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b9534-141">See also</span></span>

- [<span data-ttu-id="b9534-142">IMetaDataInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b9534-142">IMetaDataInfo Interface</span></span>](imetadatainfo-interface.md)
- [<span data-ttu-id="b9534-143">CorFileMapping 열거형</span><span class="sxs-lookup"><span data-stu-id="b9534-143">CorFileMapping Enumeration</span></span>](corfilemapping-enumeration.md)
