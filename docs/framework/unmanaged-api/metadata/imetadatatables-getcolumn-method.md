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
ms.openlocfilehash: f43d4d1547cbe92f325950e1697dada83b42c4f3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177136"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="aa786-102">IMetaDataTables::GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="aa786-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="aa786-103">지정된 열의 셀에 포함된 값에 대한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aa786-104">구문</span><span class="sxs-lookup"><span data-stu-id="aa786-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aa786-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aa786-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="aa786-106">【인】 테이블의 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="aa786-107">【인】 테이블의 열 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="aa786-108">【인】 테이블의 행 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="aa786-109">【아웃】 셀의 값에 대한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-109">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="aa786-110">설명</span><span class="sxs-lookup"><span data-stu-id="aa786-110">Remarks</span></span>

<span data-ttu-id="aa786-111">통해 `pVal` 반환되는 값의 해석은 열의 형식에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="aa786-112">열 유형은 [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md)를 호출하여 결정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="aa786-113">**GetColumn** 메서드는 **자동으로 코드 제거** 또는 **CodedToken** 형식의 열을 `mdToken` 전체 32비트 값으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="aa786-114">또한 8비트 또는 16비트 값을 전체 32비트 값으로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="aa786-115">*힙* 유형 열의 경우 반환된 *pVal은* 해당 힙에 인덱스가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="aa786-116">열 유형</span><span class="sxs-lookup"><span data-stu-id="aa786-116">Column type</span></span>              | <span data-ttu-id="aa786-117">pVal 포함</span><span class="sxs-lookup"><span data-stu-id="aa786-117">pVal contains</span></span> | <span data-ttu-id="aa786-118">주석</span><span class="sxs-lookup"><span data-stu-id="aa786-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="aa786-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="aa786-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="aa786-120">(0..63)</span><span class="sxs-lookup"><span data-stu-id="aa786-120">(0..63)</span></span>  | <span data-ttu-id="aa786-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="aa786-121">mdToken</span></span>     | <span data-ttu-id="aa786-122">*pVal에는* 전체 토큰이 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="aa786-123">이 함수는 Rid를 전체 토큰으로 자동으로 변환합니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="aa786-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="aa786-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="aa786-125">(64..95)</span><span class="sxs-lookup"><span data-stu-id="aa786-125">(64..95)</span></span> | <span data-ttu-id="aa786-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="aa786-126">mdToken</span></span> | <span data-ttu-id="aa786-127">반환 *시, pVal* 전체 토큰을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="aa786-128">이 함수는 CodedToken을 전체 토큰으로 자동으로 압축 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="aa786-129">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="aa786-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="aa786-130">Int16</span><span class="sxs-lookup"><span data-stu-id="aa786-130">Int16</span></span>         | <span data-ttu-id="aa786-131">자동으로 32비트로 확장된 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="aa786-132">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="aa786-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="aa786-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="aa786-133">UInt16</span></span>        | <span data-ttu-id="aa786-134">자동으로 32비트로 확장된 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="aa786-135">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="aa786-135">`iLONG` (98)</span></span>             | <span data-ttu-id="aa786-136">Int32</span><span class="sxs-lookup"><span data-stu-id="aa786-136">Int32</span></span>         |                                        |
| <span data-ttu-id="aa786-137">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="aa786-137">`iULONG` (99)</span></span>            | <span data-ttu-id="aa786-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="aa786-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="aa786-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="aa786-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="aa786-140">Byte</span><span class="sxs-lookup"><span data-stu-id="aa786-140">Byte</span></span>          | <span data-ttu-id="aa786-141">자동으로 32비트로 확장된 기호입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="aa786-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="aa786-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="aa786-143">문자열 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="aa786-143">String heap index</span></span> | <span data-ttu-id="aa786-144">*pVal은* 문자열 힙에 대한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="aa786-145">[IMetadataTables::GetString을](imetadatatables-getstring-method.md) 사용하여 실제 열 문자열 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="aa786-146">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="aa786-146">`iGUID` (102)</span></span>            | <span data-ttu-id="aa786-147">Guid 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="aa786-147">Guid heap index</span></span> | <span data-ttu-id="aa786-148">*pVal은* Guid 힙에 대한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="aa786-149">[I메타데이터 테이블 사용::GetGuid를](imetadatatables-getguid-method.md) 사용하여 실제 열 Guid 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="aa786-150">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="aa786-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="aa786-151">Blob 힙 인덱스</span><span class="sxs-lookup"><span data-stu-id="aa786-151">Blob heap index</span></span> | <span data-ttu-id="aa786-152">*pVal은* Blob 힙에 대한 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="aa786-153">[I메타데이터 테이블 사용::GetBlob에서](imetadatatables-getblob-method.md) 실제 열 Blob 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="aa786-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="aa786-154">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aa786-154">Requirements</span></span>  
 <span data-ttu-id="aa786-155">**플랫폼:**[시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aa786-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aa786-156">**헤더:** 코르h</span><span class="sxs-lookup"><span data-stu-id="aa786-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="aa786-157">**라이브러리:** MsCorEE.dll의 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="aa786-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="aa786-158">**.NET 프레임워크 버전**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aa786-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aa786-159">참고 항목</span><span class="sxs-lookup"><span data-stu-id="aa786-159">See also</span></span>

- [<span data-ttu-id="aa786-160">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa786-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="aa786-161">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="aa786-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
