---
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
ms.openlocfilehash: 17305f2c088dd6f479da4c823d3db0fd50c0b3d7
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74443225"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="19f12-102">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19f12-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="19f12-103">테이블에서 메타데이터 정보를 스토리지 및 검색하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="19f12-104">메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-104">Methods</span></span>  
  
|<span data-ttu-id="19f12-105">메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-105">Method</span></span>|<span data-ttu-id="19f12-106">설명</span><span class="sxs-lookup"><span data-stu-id="19f12-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="19f12-107">GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="19f12-108">지정 된 열 인덱스에 있는 BLOB (binary large object)에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="19f12-109">GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="19f12-110">BLOB 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="19f12-111">GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="19f12-112">지정 된 행 인덱스와 연결 된 토큰의 배열에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="19f12-113">GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="19f12-114">지정 된 테이블 인덱스에 있는 테이블의 지정 된 열 인덱스에 있는 열에 포함 된 값에 대 한 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="19f12-115">GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="19f12-116">지정 된 테이블의 지정 된 열에 대 한 데이터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="19f12-117">GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="19f12-118">지정 된 인덱스의 행에서 GUID를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="19f12-119">GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="19f12-120">GUID 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="19f12-121">GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="19f12-122">테이블에서 다음 BLOB의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="19f12-123">GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="19f12-124">현재 테이블 열에서 다음 GUID 값의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="19f12-125">GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="19f12-126">현재 테이블 열에서 다음 문자열의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="19f12-127">GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="19f12-128">현재 테이블 열에 하드 코딩 된 다음 문자열이 포함 된 행의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="19f12-129">GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="19f12-130">현재 `IMetaDataTables` 인스턴스의 범위에 있는 테이블 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="19f12-131">GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="19f12-132">지정 된 테이블 인덱스에 있는 테이블의 지정 된 행 인덱스에 있는 행을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="19f12-133">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="19f12-134">현재 참조 범위의 테이블 열에서 지정 된 인덱스에 있는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="19f12-135">GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="19f12-136">문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="19f12-137">GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="19f12-138">지정 된 토큰이 참조 하는 테이블의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="19f12-139">GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="19f12-140">지정 된 테이블 인덱스에 있는 테이블의 이름, 행 크기, 행 수, 열 수, 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="19f12-141">GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="19f12-142">현재 범위에 있는 문자열 열의 지정 된 인덱스에서 하드 코드 된 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="19f12-143">GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="19f12-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="19f12-144">사용자 문자열 힙의 크기 (바이트)를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="19f12-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="19f12-145">Requirements</span></span>  
 <span data-ttu-id="19f12-146">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="19f12-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="19f12-147">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="19f12-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="19f12-148">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="19f12-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="19f12-149">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="19f12-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="19f12-150">참고 항목</span><span class="sxs-lookup"><span data-stu-id="19f12-150">See also</span></span>

- [<span data-ttu-id="19f12-151">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19f12-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="19f12-152">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="19f12-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
