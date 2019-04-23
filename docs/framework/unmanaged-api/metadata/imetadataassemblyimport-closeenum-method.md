---
title: IMetaDataAssemblyImport::CloseEnum 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataAssemblyImport.CloseEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataAssemblyImport::CloseEnum
helpviewer_keywords:
- CloseEnum method, IMetaDataAssemblyImport interface [.NET Framework metadata]
- IMetaDataAssemblyImport::CloseEnum method [.NET Framework metadata]
ms.assetid: c9df4087-12b3-46d9-b075-9067dd7805df
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cc0a4f52747cbc88a26f4b9aaff6642b6c1d62f1
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59090038"
---
# <a name="imetadataassemblyimportcloseenum-method"></a><span data-ttu-id="5835f-102">IMetaDataAssemblyImport::CloseEnum 메서드</span><span class="sxs-lookup"><span data-stu-id="5835f-102">IMetaDataAssemblyImport::CloseEnum Method</span></span>
<span data-ttu-id="5835f-103">지정 된 열거형 인스턴스에 대 한 참조를 해제합니다.</span><span class="sxs-lookup"><span data-stu-id="5835f-103">Releases a reference to the specified enumeration instance.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5835f-104">구문</span><span class="sxs-lookup"><span data-stu-id="5835f-104">Syntax</span></span>  
  
```  
void CloseEnum (  
    [in] HCORENUM     hEnum  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5835f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5835f-105">Parameters</span></span>  
 `hEnum`  
 <span data-ttu-id="5835f-106">[in] 닫아야 열거형 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="5835f-106">[in] The enumeration instance to be closed.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5835f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5835f-107">Requirements</span></span>  
 <span data-ttu-id="5835f-108">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5835f-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5835f-109">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="5835f-109">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5835f-110">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="5835f-110">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5835f-111">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5835f-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5835f-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="5835f-112">See also</span></span>

- [<span data-ttu-id="5835f-113">IMetaDataAssemblyImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="5835f-113">IMetaDataAssemblyImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md)
