---
description: '자세히 알아보기: IMetaDataTables:: GetColumnInfo 메서드'
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
ms.openlocfilehash: 21980567c5f9b364362f7e3ff02ee3a5e60b01ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688236"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="b4fc2-103">IMetaDataTables::GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="b4fc2-103">IMetaDataTables::GetColumnInfo Method</span></span>

<span data-ttu-id="b4fc2-104">지정 된 테이블의 지정 된 열에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-104">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b4fc2-105">구문</span><span class="sxs-lookup"><span data-stu-id="b4fc2-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="b4fc2-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b4fc2-106">Parameters</span></span>

=======

 `ixTbl`  
 <span data-ttu-id="b4fc2-107">진행 원하는 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-107">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="b4fc2-108">진행 원하는 열의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-108">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="b4fc2-109">제한이 행에 있는 열의 오프셋에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-109">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="b4fc2-110">제한이 열의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-110">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="b4fc2-111">제한이 열에 있는 값의 형식에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-111">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="b4fc2-112">제한이 열 이름에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-112">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="b4fc2-113">설명</span><span class="sxs-lookup"><span data-stu-id="b4fc2-113">Remarks</span></span>

<span data-ttu-id="b4fc2-114">반환 된 열 유형은 값 범위 내에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-114">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="b4fc2-115">pType</span><span class="sxs-lookup"><span data-stu-id="b4fc2-115">pType</span></span>                    | <span data-ttu-id="b4fc2-116">설명</span><span class="sxs-lookup"><span data-stu-id="b4fc2-116">Description</span></span>   | <span data-ttu-id="b4fc2-117">도우미 함수</span><span class="sxs-lookup"><span data-stu-id="b4fc2-117">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="b4fc2-118">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="b4fc2-118">`0`..`iRidMax`</span></span><br><span data-ttu-id="b4fc2-119">(0, 63)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-119">(0..63)</span></span>   | <span data-ttu-id="b4fc2-120">없앨</span><span class="sxs-lookup"><span data-stu-id="b4fc2-120">Rid</span></span>           | <span data-ttu-id="b4fc2-121">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-121">**IsRidType**</span></span><br><span data-ttu-id="b4fc2-122">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-122">**IsRidOrToken**</span></span> |
| <span data-ttu-id="b4fc2-123">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="b4fc2-123">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="b4fc2-124">(64.95)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-124">(64..95)</span></span> | <span data-ttu-id="b4fc2-125">코딩 된 토큰</span><span class="sxs-lookup"><span data-stu-id="b4fc2-125">Coded token</span></span> | <span data-ttu-id="b4fc2-126">**Iscoded Tokentype**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-126">**IsCodedTokenType**</span></span> <br><span data-ttu-id="b4fc2-127">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-127">**IsRidOrToken**</span></span> |
| <span data-ttu-id="b4fc2-128">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-128">`iSHORT` (96)</span></span>            | <span data-ttu-id="b4fc2-129">Int16</span><span class="sxs-lookup"><span data-stu-id="b4fc2-129">Int16</span></span>         | <span data-ttu-id="b4fc2-130">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-130">**IsFixedType**</span></span>                   |
| <span data-ttu-id="b4fc2-131">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-131">`iUSHORT` (97)</span></span>           | <span data-ttu-id="b4fc2-132">UInt16</span><span class="sxs-lookup"><span data-stu-id="b4fc2-132">UInt16</span></span>        | <span data-ttu-id="b4fc2-133">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-133">**IsFixedType**</span></span>                   |
| <span data-ttu-id="b4fc2-134">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-134">`iLONG` (98)</span></span>             | <span data-ttu-id="b4fc2-135">Int32</span><span class="sxs-lookup"><span data-stu-id="b4fc2-135">Int32</span></span>         | <span data-ttu-id="b4fc2-136">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-136">**IsFixedType**</span></span>                   |
| <span data-ttu-id="b4fc2-137">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-137">`iULONG` (99)</span></span>            | <span data-ttu-id="b4fc2-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="b4fc2-138">UInt32</span></span>        | <span data-ttu-id="b4fc2-139">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-139">**IsFixedType**</span></span>                   |
| <span data-ttu-id="b4fc2-140">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-140">`iBYTE` (100)</span></span>            | <span data-ttu-id="b4fc2-141">Byte</span><span class="sxs-lookup"><span data-stu-id="b4fc2-141">Byte</span></span>          | <span data-ttu-id="b4fc2-142">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-142">**IsFixedType**</span></span>                   |
| <span data-ttu-id="b4fc2-143">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-143">`iSTRING` (101)</span></span>          | <span data-ttu-id="b4fc2-144">String</span><span class="sxs-lookup"><span data-stu-id="b4fc2-144">String</span></span>        | <span data-ttu-id="b4fc2-145">**I박 Aptype**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-145">**IsHeapType**</span></span>                    |
| <span data-ttu-id="b4fc2-146">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-146">`iGUID` (102)</span></span>            | <span data-ttu-id="b4fc2-147">GUID</span><span class="sxs-lookup"><span data-stu-id="b4fc2-147">Guid</span></span>          | <span data-ttu-id="b4fc2-148">**I박 Aptype**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-148">**IsHeapType**</span></span>                    |
| <span data-ttu-id="b4fc2-149">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="b4fc2-149">`iBLOB` (103)</span></span>            | <span data-ttu-id="b4fc2-150">Blob</span><span class="sxs-lookup"><span data-stu-id="b4fc2-150">Blob</span></span>          | <span data-ttu-id="b4fc2-151">**I박 Aptype**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-151">**IsHeapType**</span></span>                    |

<span data-ttu-id="b4fc2-152">다음을 사용 하 여 *힙에* 저장 된 값 (즉, `IsHeapType == true` )을 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-152">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="b4fc2-153">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-153">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="b4fc2-154">`iGUID`: **IMetadataTables**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-154">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="b4fc2-155">`iBLOB`: **IMetadataTables**</span><span class="sxs-lookup"><span data-stu-id="b4fc2-155">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b4fc2-156">위의 표에 정의 된 상수를 사용 하려면 `#define _DEFINE_META_DATA_META_CONSTANTS` *cor* 헤더 파일에서 제공 하는 지시문을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-156">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4fc2-157">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b4fc2-157">Requirements</span></span>  

 <span data-ttu-id="b4fc2-158">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b4fc2-159">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="b4fc2-159">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b4fc2-160">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b4fc2-160">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b4fc2-161">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4fc2-161">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b4fc2-162">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b4fc2-162">See also</span></span>

- [<span data-ttu-id="b4fc2-163">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4fc2-163">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b4fc2-164">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b4fc2-164">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
