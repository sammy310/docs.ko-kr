---
title: IMetaDataTables::GetString 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetString
helpviewer_keywords:
- IMetaDataTables::GetString method [.NET Framework metadata]
- GetString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 895c35cf-b95d-4e3b-93b5-cfc1cf9044fc
topic_type:
- apiref
ms.openlocfilehash: 055499230f500cb7249746e1acbf46b4548d25bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74426803"
---
# <a name="imetadatatablesgetstring-method"></a><span data-ttu-id="8f4a5-102">IMetaDataTables::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="8f4a5-102">IMetaDataTables::GetString Method</span></span>
<span data-ttu-id="8f4a5-103">Gets the string at the specified index from the table column in the current reference scope.</span><span class="sxs-lookup"><span data-stu-id="8f4a5-103">Gets the string at the specified index from the table column in the current reference scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f4a5-104">구문</span><span class="sxs-lookup"><span data-stu-id="8f4a5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetString (   
    [in]  ULONG       ixString,  
    [out] const char  **ppString  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f4a5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f4a5-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="8f4a5-106">[in] The index at which to start to search for the next value.</span><span class="sxs-lookup"><span data-stu-id="8f4a5-106">[in] The index at which to start to search for the next value.</span></span>  
  
 `ppString`  
 <span data-ttu-id="8f4a5-107">[out] A pointer to a pointer to the returned string value.</span><span class="sxs-lookup"><span data-stu-id="8f4a5-107">[out] A pointer to a pointer to the returned string value.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f4a5-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f4a5-108">Requirements</span></span>  
 <span data-ttu-id="8f4a5-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f4a5-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f4a5-110">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8f4a5-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8f4a5-111">**Library:** Used as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f4a5-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8f4a5-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f4a5-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f4a5-113">참조</span><span class="sxs-lookup"><span data-stu-id="8f4a5-113">See also</span></span>

- [<span data-ttu-id="8f4a5-114">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f4a5-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8f4a5-115">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8f4a5-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
