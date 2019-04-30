---
title: IMetaDataTables::GetTableInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 82c88c75d5799134d8c683c91e28f956743b84ba
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61992227"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="4bcbb-102">IMetaDataTables::GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="4bcbb-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="4bcbb-103">이름, 행 크기, 행의 수, 열 수 및 지정된 된 테이블의 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4bcbb-104">구문</span><span class="sxs-lookup"><span data-stu-id="4bcbb-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4bcbb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4bcbb-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="4bcbb-106">[in] 테이블의 식별자를 반환할 속성입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="4bcbb-107">[out] 테이블 행의 바이트 크기에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="4bcbb-108">[out] 테이블의 행 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="4bcbb-109">[out] 테이블의 열 개수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="4bcbb-110">[out] 키 열 또는 테이블에 키 열이 없는 경우-1의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="4bcbb-111">[out] 테이블 이름에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4bcbb-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4bcbb-112">Requirements</span></span>  
 <span data-ttu-id="4bcbb-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4bcbb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4bcbb-114">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="4bcbb-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4bcbb-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="4bcbb-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4bcbb-116">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4bcbb-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bcbb-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="4bcbb-117">See also</span></span>

- [<span data-ttu-id="4bcbb-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4bcbb-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="4bcbb-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4bcbb-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
