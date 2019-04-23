---
title: Init 메서드
ms.date: 03/30/2017
api_name:
- IALink.Init
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- Init
helpviewer_keywords:
- Init method
ms.assetid: e48b5c64-049f-4f93-ad87-d07ae9cd5845
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 60602462376543fe934bb3c58bc4988fa8ab34bf
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59119368"
---
# <a name="init-method"></a><span data-ttu-id="f702b-102">Init 메서드</span><span class="sxs-lookup"><span data-stu-id="f702b-102">Init Method</span></span>
<span data-ttu-id="f702b-103">구현 하는 개체를 준비 합니다 [IALink 인터페이스](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f702b-103">Prepares objects implementing the [IALink Interface](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f702b-104">구문</span><span class="sxs-lookup"><span data-stu-id="f702b-104">Syntax</span></span>  
  
```  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="f702b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f702b-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="f702b-106">[IMetaDataDispenserEx 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) 디스펜서 메타 데이터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f702b-106">[IMetaDataDispenserEx Interface](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="f702b-107">[IMetaDataError 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) 인터페이스를 처리 하는 선택적 오류에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f702b-107">[IMetaDataError Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f702b-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="f702b-108">Return Value</span></span>  
 <span data-ttu-id="f702b-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="f702b-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f702b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f702b-110">Requirements</span></span>  
 <span data-ttu-id="f702b-111">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="f702b-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f702b-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="f702b-112">See also</span></span>

- [<span data-ttu-id="f702b-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f702b-113">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="f702b-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f702b-114">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="f702b-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="f702b-115">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
