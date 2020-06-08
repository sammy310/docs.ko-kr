---
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
ms.openlocfilehash: 76d23fe9221ae5a07d79b8c5c1a7ad297922b003
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501250"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="88c25-102">IMetaDataTables::GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="88c25-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="88c25-103">지정 된 테이블에 있는 지정 된 열 및 행의 셀에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="88c25-104">구문</span><span class="sxs-lookup"><span data-stu-id="88c25-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="88c25-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="88c25-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="88c25-106">진행 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="88c25-107">진행 테이블에 있는 열의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="88c25-108">진행 테이블에 있는 행의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="88c25-109">제한이 셀의 값에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="88c25-110">설명</span><span class="sxs-lookup"><span data-stu-id="88c25-110">Remarks</span></span>

<span data-ttu-id="88c25-111">를 통해 반환 되는 값의 interpretion는 `pVal` 열의 형식에 따라 달라 집니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="88c25-112">열 유형은 [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md)을 호출 하 여 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="88c25-113">**Getcolumn** 메서드는 **Rid** 또는 **codedtoken** 형식의 열을 전체 32 비트 값으로 자동으로 변환 `mdToken` 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="88c25-114">또한 8 비트 또는 16 비트 값을 자동으로 전체 32 비트 값으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="88c25-115">*힙* 유형 열의 경우 반환 된 *pVal* 는 해당 힙의 인덱스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="88c25-116">열 유형</span><span class="sxs-lookup"><span data-stu-id="88c25-116">Column type</span></span>              | <span data-ttu-id="88c25-117">pVal contains</span><span class="sxs-lookup"><span data-stu-id="88c25-117">pVal contains</span></span> | <span data-ttu-id="88c25-118">설명</span><span class="sxs-lookup"><span data-stu-id="88c25-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="88c25-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="88c25-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="88c25-120">(0, 63)</span><span class="sxs-lookup"><span data-stu-id="88c25-120">(0..63)</span></span>  | <span data-ttu-id="88c25-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="88c25-121">mdToken</span></span>     | <span data-ttu-id="88c25-122">*pVal* 에는 전체 토큰이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="88c25-123">함수는 Rid를 전체 토큰으로 자동으로 변환 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="88c25-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="88c25-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="88c25-125">(64.95)</span><span class="sxs-lookup"><span data-stu-id="88c25-125">(64..95)</span></span> | <span data-ttu-id="88c25-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="88c25-126">mdToken</span></span> | <span data-ttu-id="88c25-127">반환 될 때 *pVal* 는 전체 토큰을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="88c25-128">함수는 CodedToken의 압축을 자동으로 전체 토큰으로 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="88c25-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="88c25-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="88c25-130">Int16</span><span class="sxs-lookup"><span data-stu-id="88c25-130">Int16</span></span>         | <span data-ttu-id="88c25-131">자동으로 32 비트에 자동으로 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="88c25-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="88c25-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="88c25-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="88c25-133">UInt16</span></span>        | <span data-ttu-id="88c25-134">자동으로 32 비트에 자동으로 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="88c25-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="88c25-135">`iLONG` (98)</span></span>             | <span data-ttu-id="88c25-136">Int32</span><span class="sxs-lookup"><span data-stu-id="88c25-136">Int32</span></span>         |                                        |
| <span data-ttu-id="88c25-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="88c25-137">`iULONG` (99)</span></span>            | <span data-ttu-id="88c25-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="88c25-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="88c25-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="88c25-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="88c25-140">Byte</span><span class="sxs-lookup"><span data-stu-id="88c25-140">Byte</span></span>          | <span data-ttu-id="88c25-141">자동으로 32 비트에 자동으로 서명 합니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="88c25-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="88c25-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="88c25-143">문자열 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="88c25-143">String heap index</span></span> | <span data-ttu-id="88c25-144">*pVal* 은 문자열 힙에 대 한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="88c25-145">[IMetadataTables:: GetString](imetadatatables-getstring-method.md) 를 사용 하 여 실제 열 문자열 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="88c25-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="88c25-146">`iGUID` (102)</span></span>            | <span data-ttu-id="88c25-147">Guid 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="88c25-147">Guid heap index</span></span> | <span data-ttu-id="88c25-148">*pVal* 는 Guid 힙의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="88c25-149">[IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) 를 사용 하 여 실제 열 Guid 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="88c25-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="88c25-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="88c25-151">Blob 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="88c25-151">Blob heap index</span></span> | <span data-ttu-id="88c25-152">*pVal* 는 Blob 힙에 대 한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="88c25-153">[IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) 을 사용 하 여 실제 열 Blob 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="88c25-154">요구 사항</span><span class="sxs-lookup"><span data-stu-id="88c25-154">Requirements</span></span>  
 <span data-ttu-id="88c25-155">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="88c25-155">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="88c25-156">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="88c25-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="88c25-157">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="88c25-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="88c25-158">**.NET Framework 버전**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="88c25-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="88c25-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="88c25-159">See also</span></span>

- [<span data-ttu-id="88c25-160">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88c25-160">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="88c25-161">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="88c25-161">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
