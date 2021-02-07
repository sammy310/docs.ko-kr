---
description: '자세히 알아보기: Init 메서드'
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
ms.openlocfilehash: 531e05a09cbecbfb67c8c004d1e4ba1deb7e59a0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662561"
---
# <a name="init-method"></a><span data-ttu-id="292a5-103">Init 메서드</span><span class="sxs-lookup"><span data-stu-id="292a5-103">Init Method</span></span>

<span data-ttu-id="292a5-104">사용할 [Ialink 인터페이스](ialink-interface.md) 를 구현 하는 개체를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="292a5-104">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="292a5-105">구문</span><span class="sxs-lookup"><span data-stu-id="292a5-105">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="292a5-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="292a5-106">Parameters</span></span>  

 `pDispenser`  
 <span data-ttu-id="292a5-107">메타 데이터 디스펜서에 대 한 [IMetaDataDispenserEx 인터페이스](../metadata/imetadatadispenserex-interface.md) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="292a5-107">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="292a5-108">선택적 오류 처리 인터페이스에 대 한 [IMetaDataError 인터페이스](../metadata/imetadataerror-interface.md) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="292a5-108">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="292a5-109">Return Value</span><span class="sxs-lookup"><span data-stu-id="292a5-109">Return Value</span></span>  

 <span data-ttu-id="292a5-110">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="292a5-110">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="292a5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="292a5-111">Requirements</span></span>  

 <span data-ttu-id="292a5-112">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="292a5-112">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="292a5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="292a5-113">See also</span></span>

- [<span data-ttu-id="292a5-114">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="292a5-114">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="292a5-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="292a5-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="292a5-116">ALink API</span><span class="sxs-lookup"><span data-stu-id="292a5-116">ALink API</span></span>](index.md)
