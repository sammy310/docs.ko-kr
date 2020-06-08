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
ms.openlocfilehash: 7e60dd9535809ca13f3bbe6ac76f5ea1209df734
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501178"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="dc6f1-102">IMetaDataTables::GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="dc6f1-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="dc6f1-103">지정 된 테이블의 이름, 행 크기, 행 수, 열 수, 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="dc6f1-104">구문</span><span class="sxs-lookup"><span data-stu-id="dc6f1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="dc6f1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="dc6f1-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="dc6f1-106">진행 반환할 속성을 가진 테이블의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="dc6f1-107">제한이 테이블 행의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="dc6f1-108">제한이 테이블의 행 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="dc6f1-109">제한이 테이블의 열 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="dc6f1-110">제한이 키 열의 인덱스에 대 한 포인터 이거나, 테이블에 키 열이 없으면-1입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="dc6f1-111">제한이 테이블 이름에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="dc6f1-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="dc6f1-112">Requirements</span></span>  
 <span data-ttu-id="dc6f1-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dc6f1-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="dc6f1-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dc6f1-115">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="dc6f1-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dc6f1-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dc6f1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dc6f1-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="dc6f1-117">See also</span></span>

- [<span data-ttu-id="dc6f1-118">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc6f1-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="dc6f1-119">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="dc6f1-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
