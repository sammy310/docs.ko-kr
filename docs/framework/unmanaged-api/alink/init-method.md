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
ms.openlocfilehash: bf96770dd58c9b84596c082a615f626ec723cc6c
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787241"
---
# <a name="init-method"></a><span data-ttu-id="c5b4d-102">Init 메서드</span><span class="sxs-lookup"><span data-stu-id="c5b4d-102">Init Method</span></span>
<span data-ttu-id="c5b4d-103">사용할 [Ialink 인터페이스](ialink-interface.md) 를 구현 하는 개체를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b4d-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c5b4d-104">구문</span><span class="sxs-lookup"><span data-stu-id="c5b4d-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c5b4d-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c5b4d-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="c5b4d-106">메타 데이터 디스펜서에 대 한 [IMetaDataDispenserEx 인터페이스](../metadata/imetadatadispenserex-interface.md) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b4d-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="c5b4d-107">선택적 오류 처리 인터페이스에 대 한 [IMetaDataError 인터페이스](../metadata/imetadataerror-interface.md) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="c5b4d-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c5b4d-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="c5b4d-108">Return Value</span></span>  
 <span data-ttu-id="c5b4d-109">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c5b4d-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c5b4d-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c5b4d-110">Requirements</span></span>  
 <span data-ttu-id="c5b4d-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="c5b4d-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5b4d-112">참고자료</span><span class="sxs-lookup"><span data-stu-id="c5b4d-112">See also</span></span>

- [<span data-ttu-id="c5b4d-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5b4d-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c5b4d-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c5b4d-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c5b4d-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="c5b4d-115">ALink API</span></span>](index.md)
