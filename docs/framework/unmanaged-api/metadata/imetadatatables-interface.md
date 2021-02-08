---
description: '자세히 알아보기: IMetaDataTables 인터페이스'
title: IMetaDataTables 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: c3edf504586bad1252c36d6e8254193eaf9cc26d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799272"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="411ff-103">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="411ff-103">IMetaDataTables Interface</span></span>

<span data-ttu-id="411ff-104">테이블에서 메타데이터 정보를 스토리지 및 검색하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-104">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="411ff-105">메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-105">Methods</span></span>  
  
|<span data-ttu-id="411ff-106">메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-106">Method</span></span>|<span data-ttu-id="411ff-107">설명</span><span class="sxs-lookup"><span data-stu-id="411ff-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="411ff-108">GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-108">GetBlob Method</span></span>](imetadatatables-getblob-method.md)|<span data-ttu-id="411ff-109">지정 된 열 인덱스에 있는 BLOB (binary large object)에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-109">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="411ff-110">GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-110">GetBlobHeapSize Method</span></span>](imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="411ff-111">BLOB 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-111">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="411ff-112">GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-112">GetCodedTokenInfo Method</span></span>](imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="411ff-113">지정 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-113">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="411ff-114">GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-114">GetColumn Method</span></span>](imetadatatables-getcolumn-method.md)|<span data-ttu-id="411ff-115">지정 된 테이블 인덱스에 있는 테이블의 지정 된 열 인덱스에 있는 열에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-115">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="411ff-116">GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-116">GetColumnInfo Method</span></span>](imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="411ff-117">지정 된 테이블의 지정 된 열에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-117">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="411ff-118">GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-118">GetGuid Method</span></span>](imetadatatables-getguid-method.md)|<span data-ttu-id="411ff-119">지정 된 인덱스의 행에서 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-119">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="411ff-120">GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-120">GetGuidHeapSize Method</span></span>](imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="411ff-121">GUID 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-121">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="411ff-122">GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-122">GetNextBlob Method</span></span>](imetadatatables-getnextblob-method.md)|<span data-ttu-id="411ff-123">테이블에서 다음 BLOB의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-123">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="411ff-124">GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-124">GetNextGuid Method</span></span>](imetadatatables-getnextguid-method.md)|<span data-ttu-id="411ff-125">현재 테이블 열에서 다음 GUID 값의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-125">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="411ff-126">GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-126">GetNextString Method</span></span>](imetadatatables-getnextstring-method.md)|<span data-ttu-id="411ff-127">현재 테이블 열에서 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-127">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="411ff-128">GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-128">GetNextUserString Method</span></span>](imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="411ff-129">현재 테이블 열에 하드 코딩 된 다음 문자열이 포함 된 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-129">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="411ff-130">GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-130">GetNumTables Method</span></span>](imetadatatables-getnumtables-method.md)|<span data-ttu-id="411ff-131">현재 인스턴스의 범위에 있는 테이블 수를 가져옵니다 `IMetaDataTables` .</span><span class="sxs-lookup"><span data-stu-id="411ff-131">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="411ff-132">GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-132">GetRow Method</span></span>](imetadatatables-getrow-method.md)|<span data-ttu-id="411ff-133">지정 된 테이블 인덱스에 있는 테이블의 지정 된 행 인덱스에 있는 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-133">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="411ff-134">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-134">GetString Method</span></span>](imetadatatables-getstring-method.md)|<span data-ttu-id="411ff-135">현재 참조 범위의 테이블 열에서 지정 된 인덱스에 있는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-135">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="411ff-136">GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-136">GetStringHeapSize Method</span></span>](imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="411ff-137">문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-137">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="411ff-138">GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-138">GetTableIndex Method</span></span>](imetadatatables-gettableindex-method.md)|<span data-ttu-id="411ff-139">지정 된 토큰이 참조 하는 테이블의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-139">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="411ff-140">GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-140">GetTableInfo Method</span></span>](imetadatatables-gettableinfo-method.md)|<span data-ttu-id="411ff-141">지정 된 테이블 인덱스에 있는 테이블의 이름, 행 크기, 행 수, 열 수, 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-141">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="411ff-142">GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-142">GetUserString Method</span></span>](imetadatatables-getuserstring-method.md)|<span data-ttu-id="411ff-143">현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-143">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="411ff-144">GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="411ff-144">GetUserStringHeapSize Method</span></span>](imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="411ff-145">사용자 문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-145">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="411ff-146">요구 사항</span><span class="sxs-lookup"><span data-stu-id="411ff-146">Requirements</span></span>  

 <span data-ttu-id="411ff-147">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="411ff-147">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="411ff-148">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="411ff-148">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="411ff-149">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="411ff-149">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="411ff-150">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="411ff-150">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="411ff-151">참고 항목</span><span class="sxs-lookup"><span data-stu-id="411ff-151">See also</span></span>

- [<span data-ttu-id="411ff-152">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="411ff-152">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="411ff-153">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="411ff-153">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
