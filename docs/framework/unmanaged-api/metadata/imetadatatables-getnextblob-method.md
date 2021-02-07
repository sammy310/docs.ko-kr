---
description: '자세히 알아보기: IMetaDataTables:: GetNextBlob 메서드'
title: IMetaDataTables::GetNextBlob 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextBlob
helpviewer_keywords:
- IMetaDataTables::GetNextBlob method [.NET Framework metadata]
- GetNextBlob method [.NET Framework metadata]
ms.assetid: 017c8ab4-4c09-4754-9935-5b0b49cabecb
topic_type:
- apiref
ms.openlocfilehash: 99126ab5c3891ee09346bb54096a4fce3ca44bc5
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688132"
---
# <a name="imetadatatablesgetnextblob-method"></a><span data-ttu-id="be092-103">IMetaDataTables::GetNextBlob 메서드</span><span class="sxs-lookup"><span data-stu-id="be092-103">IMetaDataTables::GetNextBlob Method</span></span>

<span data-ttu-id="be092-104">테이블에서 다음 BLOB (binary large object)의 인덱스를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="be092-104">Gets the index of the next binary large object (BLOB) in the table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be092-105">구문</span><span class="sxs-lookup"><span data-stu-id="be092-105">Syntax</span></span>  
  
```cpp  
HRESULT GetNextBlob (  
    [in]  ULONG   ixBlob,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="be092-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="be092-106">Parameters</span></span>  

 `ixBlob`  
 <span data-ttu-id="be092-107">진행 Blob의 열에서 반환 된 인덱스입니다.</span><span class="sxs-lookup"><span data-stu-id="be092-107">[in] The index, as returned from a column of BLOBs.</span></span>  
  
 `pNext`  
 <span data-ttu-id="be092-108">제한이 다음 BLOB의 인덱스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="be092-108">[out] A pointer to the index of the next BLOB.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="be092-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be092-109">Requirements</span></span>  

 <span data-ttu-id="be092-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be092-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be092-111">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="be092-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="be092-112">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="be092-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="be092-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="be092-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="be092-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="be092-114">See also</span></span>

- [<span data-ttu-id="be092-115">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be092-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="be092-116">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="be092-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
