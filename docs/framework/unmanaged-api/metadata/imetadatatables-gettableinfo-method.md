---
description: '자세히 알아보기: IMetaDataTables:: GetTableInfo 메서드'
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
ms.openlocfilehash: 3929f91c15b5c1fc22ac3ad4b17cbaa38a08533a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687651"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="4a226-103">IMetaDataTables::GetTableInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="4a226-103">IMetaDataTables::GetTableInfo Method</span></span>

<span data-ttu-id="4a226-104">지정 된 테이블의 이름, 행 크기, 행 수, 열 수, 키 열 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-104">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4a226-105">구문</span><span class="sxs-lookup"><span data-stu-id="4a226-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="4a226-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4a226-106">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="4a226-107">진행 반환할 속성을 가진 테이블의 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-107">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="4a226-108">제한이 테이블 행의 크기 (바이트)에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-108">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="4a226-109">제한이 테이블의 행 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-109">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="4a226-110">제한이 테이블의 열 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-110">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="4a226-111">제한이 키 열의 인덱스에 대 한 포인터 이거나, 테이블에 키 열이 없으면-1입니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-111">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="4a226-112">제한이 테이블 이름에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-112">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4a226-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4a226-113">Requirements</span></span>  

 <span data-ttu-id="4a226-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4a226-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4a226-115">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="4a226-115">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4a226-116">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4a226-116">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4a226-117">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4a226-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4a226-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4a226-118">See also</span></span>

- [<span data-ttu-id="4a226-119">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a226-119">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="4a226-120">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4a226-120">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
