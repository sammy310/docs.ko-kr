---
title: IMetaDataTables::GetColumnInfo 메서드
ms.date: 10/10/2019
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177130"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="c2d0d-102">IMetaDataTables::GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="c2d0d-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="c2d0d-103">지정된 테이블에서 지정된 열에 대한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c2d0d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c2d0d-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c2d0d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c2d0d-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="c2d0d-106">【인】 원하는 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="c2d0d-107">【인】 원하는 열의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="c2d0d-108">【아웃】 행의 열 오프셋에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="c2d0d-109">【아웃】 열의 크기에 대한 포인터(바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="c2d0d-110">【아웃】 열의 값 유형에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="c2d0d-111">【아웃】 열 이름에 대한 포인터에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="c2d0d-112">설명</span><span class="sxs-lookup"><span data-stu-id="c2d0d-112">Remarks</span></span>

<span data-ttu-id="c2d0d-113">반환된 열 유형은 값 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="c2d0d-114">p유형</span><span class="sxs-lookup"><span data-stu-id="c2d0d-114">pType</span></span>                    | <span data-ttu-id="c2d0d-115">Description</span><span class="sxs-lookup"><span data-stu-id="c2d0d-115">Description</span></span>   | <span data-ttu-id="c2d0d-116">도우미 기능</span><span class="sxs-lookup"><span data-stu-id="c2d0d-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="c2d0d-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="c2d0d-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="c2d0d-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-118">(0..63)</span></span>   | <span data-ttu-id="c2d0d-119">제거</span><span class="sxs-lookup"><span data-stu-id="c2d0d-119">Rid</span></span>           | <span data-ttu-id="c2d0d-120">**이스리드 타입**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-120">**IsRidType**</span></span><br><span data-ttu-id="c2d0d-121">**이리도르 토큰**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="c2d0d-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="c2d0d-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="c2d0d-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-123">(64..95)</span></span> | <span data-ttu-id="c2d0d-124">코딩된 토큰</span><span class="sxs-lookup"><span data-stu-id="c2d0d-124">Coded token</span></span> | <span data-ttu-id="c2d0d-125">**IsCoded토큰 타입**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="c2d0d-126">**이리도르 토큰**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="c2d0d-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="c2d0d-128">Int16</span><span class="sxs-lookup"><span data-stu-id="c2d0d-128">Int16</span></span>         | <span data-ttu-id="c2d0d-129">**IsfixedType**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c2d0d-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="c2d0d-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="c2d0d-131">UInt16</span></span>        | <span data-ttu-id="c2d0d-132">**IsfixedType**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c2d0d-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-133">`iLONG` (98)</span></span>             | <span data-ttu-id="c2d0d-134">Int32</span><span class="sxs-lookup"><span data-stu-id="c2d0d-134">Int32</span></span>         | <span data-ttu-id="c2d0d-135">**IsfixedType**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c2d0d-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-136">`iULONG` (99)</span></span>            | <span data-ttu-id="c2d0d-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="c2d0d-137">UInt32</span></span>        | <span data-ttu-id="c2d0d-138">**IsfixedType**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c2d0d-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="c2d0d-140">Byte</span><span class="sxs-lookup"><span data-stu-id="c2d0d-140">Byte</span></span>          | <span data-ttu-id="c2d0d-141">**IsfixedType**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="c2d0d-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="c2d0d-143">String</span><span class="sxs-lookup"><span data-stu-id="c2d0d-143">String</span></span>        | <span data-ttu-id="c2d0d-144">**이시압 타입**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="c2d0d-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-145">`iGUID` (102)</span></span>            | <span data-ttu-id="c2d0d-146">Guid</span><span class="sxs-lookup"><span data-stu-id="c2d0d-146">Guid</span></span>          | <span data-ttu-id="c2d0d-147">**이시압 타입**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="c2d0d-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="c2d0d-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="c2d0d-149">Blob</span><span class="sxs-lookup"><span data-stu-id="c2d0d-149">Blob</span></span>          | <span data-ttu-id="c2d0d-150">**이시압 타입**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="c2d0d-151">*힙에* 저장된 값(즉,)을 `IsHeapType == true`사용하여 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="c2d0d-152">`iSTRING`: **I메타데이터 테이블.겟스트링**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="c2d0d-153">`iGUID`: **I메타데이터 테이블.겟가드**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="c2d0d-154">`iBLOB`: **I메타데이터 테이블.겟블블**</span><span class="sxs-lookup"><span data-stu-id="c2d0d-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c2d0d-155">위의 표에 정의된 상수를 사용하려면 `#define _DEFINE_META_DATA_META_CONSTANTS` *cor.h* 헤더 파일에서 제공하는 지시문을 포함하십시오.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="c2d0d-156">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c2d0d-156">Requirements</span></span>  
 <span data-ttu-id="c2d0d-157">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c2d0d-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2d0d-158">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="c2d0d-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c2d0d-159">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="c2d0d-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c2d0d-160">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2d0d-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2d0d-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c2d0d-161">See also</span></span>

- [<span data-ttu-id="c2d0d-162">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2d0d-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c2d0d-163">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c2d0d-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
