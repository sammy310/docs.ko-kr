---
description: '자세히 알아보기: IMetaDataTables:: GetColumn 메서드'
title: IMetaDataTables::GetColumn 메서드
ms.date: 02/25/2019
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
ms.openlocfilehash: 4c4cec7216f93783b34b594330358d1e6036ed40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688275"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="27077-103">IMetaDataTables::GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="27077-103">IMetaDataTables::GetColumn Method</span></span>

<span data-ttu-id="27077-104">지정 된 테이블에 있는 지정 된 열 및 행의 셀에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27077-104">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27077-105">구문</span><span class="sxs-lookup"><span data-stu-id="27077-105">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="27077-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="27077-106">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="27077-107">진행 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-107">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="27077-108">진행 테이블에 있는 열의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-108">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="27077-109">진행 테이블에 있는 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-109">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="27077-110">제한이 셀의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-110">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="27077-111">설명</span><span class="sxs-lookup"><span data-stu-id="27077-111">Remarks</span></span>

<span data-ttu-id="27077-112">를 통해 반환 되는 값의 interpretion는 `pVal` 열의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="27077-112">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="27077-113">열 유형은 [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md)을 호출 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="27077-113">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="27077-114">**Getcolumn** 메서드는 **Rid** 또는 **codedtoken** 형식의 열을 전체 32 비트 값으로 자동으로 변환 `mdToken` 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-114">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="27077-115">또한 8 비트 또는 16 비트 값을 자동으로 전체 32 비트 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-115">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="27077-116">*힙* 유형 열의 경우 반환 된 *pVal* 는 해당 힙의 인덱스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27077-116">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="27077-117">열 유형</span><span class="sxs-lookup"><span data-stu-id="27077-117">Column type</span></span>              | <span data-ttu-id="27077-118">pVal contains</span><span class="sxs-lookup"><span data-stu-id="27077-118">pVal contains</span></span> | <span data-ttu-id="27077-119">의견</span><span class="sxs-lookup"><span data-stu-id="27077-119">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="27077-120">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="27077-120">`0`..`iRidMax`</span></span><br><span data-ttu-id="27077-121">(0, 63)</span><span class="sxs-lookup"><span data-stu-id="27077-121">(0..63)</span></span>  | <span data-ttu-id="27077-122">mdToken</span><span class="sxs-lookup"><span data-stu-id="27077-122">mdToken</span></span>     | <span data-ttu-id="27077-123">*pVal* 에는 전체 토큰이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27077-123">*pVal* will contain a full Token.</span></span> <span data-ttu-id="27077-124">함수는 Rid를 전체 토큰으로 자동으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-124">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="27077-125">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="27077-125">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="27077-126">(64.95)</span><span class="sxs-lookup"><span data-stu-id="27077-126">(64..95)</span></span> | <span data-ttu-id="27077-127">mdToken</span><span class="sxs-lookup"><span data-stu-id="27077-127">mdToken</span></span> | <span data-ttu-id="27077-128">반환 될 때 *pVal* 는 전체 토큰을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-128">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="27077-129">함수는 CodedToken의 압축을 자동으로 전체 토큰으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="27077-129">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="27077-130">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="27077-130">`iSHORT` (96)</span></span>            | <span data-ttu-id="27077-131">Int16</span><span class="sxs-lookup"><span data-stu-id="27077-131">Int16</span></span>         | <span data-ttu-id="27077-132">자동으로 32 비트에 자동으로 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-132">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="27077-133">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="27077-133">`iUSHORT` (97)</span></span>           | <span data-ttu-id="27077-134">UInt16</span><span class="sxs-lookup"><span data-stu-id="27077-134">UInt16</span></span>        | <span data-ttu-id="27077-135">자동으로 32 비트에 자동으로 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-135">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="27077-136">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="27077-136">`iLONG` (98)</span></span>             | <span data-ttu-id="27077-137">Int32</span><span class="sxs-lookup"><span data-stu-id="27077-137">Int32</span></span>         |                                        |
| <span data-ttu-id="27077-138">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="27077-138">`iULONG` (99)</span></span>            | <span data-ttu-id="27077-139">UInt32</span><span class="sxs-lookup"><span data-stu-id="27077-139">UInt32</span></span>        |                                        |
| <span data-ttu-id="27077-140">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="27077-140">`iBYTE` (100)</span></span>            | <span data-ttu-id="27077-141">Byte</span><span class="sxs-lookup"><span data-stu-id="27077-141">Byte</span></span>          | <span data-ttu-id="27077-142">자동으로 32 비트에 자동으로 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="27077-142">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="27077-143">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="27077-143">`iSTRING` (101)</span></span>          | <span data-ttu-id="27077-144">문자열 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="27077-144">String heap index</span></span> | <span data-ttu-id="27077-145">*pVal* 은 문자열 힙에 대 한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-145">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="27077-146">[IMetadataTables:: GetString](imetadatatables-getstring-method.md) 를 사용 하 여 실제 열 문자열 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27077-146">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="27077-147">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="27077-147">`iGUID` (102)</span></span>            | <span data-ttu-id="27077-148">Guid 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="27077-148">Guid heap index</span></span> | <span data-ttu-id="27077-149">*pVal* 는 Guid 힙의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-149">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="27077-150">[IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) 를 사용 하 여 실제 열 Guid 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27077-150">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="27077-151">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="27077-151">`iBLOB` (103)</span></span>            | <span data-ttu-id="27077-152">Blob 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="27077-152">Blob heap index</span></span> | <span data-ttu-id="27077-153">*pVal* 는 Blob 힙에 대 한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="27077-153">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="27077-154">[IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) 을 사용 하 여 실제 열 Blob 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="27077-154">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="27077-155">요구 사항</span><span class="sxs-lookup"><span data-stu-id="27077-155">Requirements</span></span>  

 <span data-ttu-id="27077-156">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="27077-156">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27077-157">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="27077-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="27077-158">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="27077-158">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27077-159">**.NET Framework 버전**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27077-159">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27077-160">참고 항목</span><span class="sxs-lookup"><span data-stu-id="27077-160">See also</span></span>

- [<span data-ttu-id="27077-161">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27077-161">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="27077-162">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="27077-162">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
