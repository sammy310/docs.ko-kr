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
# <a name="imetadatatables-interface"></a><span data-ttu-id="2dd53-102">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd53-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="2dd53-103">테이블에서 메타데이터 정보를 스토리지 및 검색하는 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2dd53-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2dd53-104">메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-104">Methods</span></span>  
  
|<span data-ttu-id="2dd53-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-105">Method</span></span>|<span data-ttu-id="2dd53-106">설명</span><span class="sxs-lookup"><span data-stu-id="2dd53-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2dd53-107">GetBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-107">GetBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblob-method.md)|<span data-ttu-id="2dd53-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span><span class="sxs-lookup"><span data-stu-id="2dd53-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="2dd53-109">GetBlobHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-109">GetBlobHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="2dd53-110">Gets the size, in bytes, of the BLOB heap.</span><span class="sxs-lookup"><span data-stu-id="2dd53-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="2dd53-111">GetCodedTokenInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-111">GetCodedTokenInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="2dd53-112">Gets a pointer to an array of tokens associated with the specified row index.</span><span class="sxs-lookup"><span data-stu-id="2dd53-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="2dd53-113">GetColumn 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-113">GetColumn Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumn-method.md)|<span data-ttu-id="2dd53-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span><span class="sxs-lookup"><span data-stu-id="2dd53-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="2dd53-115">GetColumnInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-115">GetColumnInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="2dd53-116">Gets data about the specified column in the specified table.</span><span class="sxs-lookup"><span data-stu-id="2dd53-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="2dd53-117">GetGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-117">GetGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguid-method.md)|<span data-ttu-id="2dd53-118">Gets a GUID from the row at the specified index.</span><span class="sxs-lookup"><span data-stu-id="2dd53-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="2dd53-119">GetGuidHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-119">GetGuidHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="2dd53-120">Gets the size, in bytes, of the GUID heap.</span><span class="sxs-lookup"><span data-stu-id="2dd53-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="2dd53-121">GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-121">GetNextBlob Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextblob-method.md)|<span data-ttu-id="2dd53-122">Gets the index of the next BLOB in the table.</span><span class="sxs-lookup"><span data-stu-id="2dd53-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="2dd53-123">GetNextGuid 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-123">GetNextGuid Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextguid-method.md)|<span data-ttu-id="2dd53-124">Gets the index of the next GUID value in the current table column.</span><span class="sxs-lookup"><span data-stu-id="2dd53-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="2dd53-125">GetNextString 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-125">GetNextString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextstring-method.md)|<span data-ttu-id="2dd53-126">Gets the index of the next string in the current table column.</span><span class="sxs-lookup"><span data-stu-id="2dd53-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="2dd53-127">GetNextUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-127">GetNextUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="2dd53-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span><span class="sxs-lookup"><span data-stu-id="2dd53-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="2dd53-129">GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-129">GetNumTables Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getnumtables-method.md)|<span data-ttu-id="2dd53-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span><span class="sxs-lookup"><span data-stu-id="2dd53-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="2dd53-131">GetRow 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-131">GetRow Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getrow-method.md)|<span data-ttu-id="2dd53-132">Gets the row at the specified row index, in the table at the specified table index.</span><span class="sxs-lookup"><span data-stu-id="2dd53-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="2dd53-133">GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-133">GetString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstring-method.md)|<span data-ttu-id="2dd53-134">Gets the string at the specified index from the table column in the current reference scope.</span><span class="sxs-lookup"><span data-stu-id="2dd53-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="2dd53-135">GetStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-135">GetStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="2dd53-136">Gets the size, in bytes, of the string heap.</span><span class="sxs-lookup"><span data-stu-id="2dd53-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="2dd53-137">GetTableIndex 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-137">GetTableIndex Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableindex-method.md)|<span data-ttu-id="2dd53-138">Gets the index for the table referenced by the specified token.</span><span class="sxs-lookup"><span data-stu-id="2dd53-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="2dd53-139">GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-139">GetTableInfo Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-gettableinfo-method.md)|<span data-ttu-id="2dd53-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span><span class="sxs-lookup"><span data-stu-id="2dd53-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="2dd53-141">GetUserString 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-141">GetUserString Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstring-method.md)|<span data-ttu-id="2dd53-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span><span class="sxs-lookup"><span data-stu-id="2dd53-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="2dd53-143">GetUserStringHeapSize 메서드</span><span class="sxs-lookup"><span data-stu-id="2dd53-143">GetUserStringHeapSize Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="2dd53-144">Gets the size, in bytes, of the user string heap.</span><span class="sxs-lookup"><span data-stu-id="2dd53-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2dd53-145">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2dd53-145">Requirements</span></span>  
 <span data-ttu-id="2dd53-146">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2dd53-146">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2dd53-147">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2dd53-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2dd53-148">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2dd53-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2dd53-149">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2dd53-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2dd53-150">참조</span><span class="sxs-lookup"><span data-stu-id="2dd53-150">See also</span></span>

- [<span data-ttu-id="2dd53-151">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd53-151">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
- [<span data-ttu-id="2dd53-152">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2dd53-152">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
