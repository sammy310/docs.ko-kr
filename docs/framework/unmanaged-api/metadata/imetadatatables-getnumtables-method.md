---
title: IMetaDataTables::GetNumTables 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNumTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNumTables
helpviewer_keywords:
- GetNumTables method [.NET Framework metadata]
- IMetaDataTables::GetNumTables method [.NET Framework metadata]
ms.assetid: 8196f2a3-bbf2-45d3-a6cd-74502c356644
topic_type:
- apiref
ms.openlocfilehash: ab864b251a989056bc34b2c7c6658964556f9ac1
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449502"
---
# <a name="imetadatatablesgetnumtables-method"></a><span data-ttu-id="c5660-102">IMetaDataTables::GetNumTables 메서드</span><span class="sxs-lookup"><span data-stu-id="c5660-102">IMetaDataTables::GetNumTables Method</span></span>
<span data-ttu-id="c5660-103">현재 `IMetaDataTables` 인스턴스의 범위에 있는 테이블 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c5660-103">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5660-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5660-104">Syntax</span></span>  
  
```cpp  
HRESULT GetNumTables (  
    [out]  ULONG   *pcTables  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5660-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5660-105">Parameters</span></span>  
 `pcTables`  
 <span data-ttu-id="c5660-106">제한이 현재 인스턴스 범위의 테이블 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5660-106">[out] A pointer to the number of tables in the current instance scope.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5660-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5660-107">Requirements</span></span>  
 <span data-ttu-id="c5660-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="c5660-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5660-109">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="c5660-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c5660-110">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="c5660-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c5660-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5660-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5660-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c5660-112">See also</span></span>

- [<span data-ttu-id="c5660-113">IMetaDataTables 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5660-113">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="c5660-114">IMetaDataTables2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5660-114">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
