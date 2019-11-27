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
ms.openlocfilehash: 986ae69e7ebb8f607be5d37fab426bcc787abb26
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445645"
---
# <a name="init-method"></a><span data-ttu-id="b29c3-102">Init 메서드</span><span class="sxs-lookup"><span data-stu-id="b29c3-102">Init Method</span></span>
<span data-ttu-id="b29c3-103">사용할 [Ialink 인터페이스](ialink-interface.md) 를 구현 하는 개체를 준비 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29c3-103">Prepares objects implementing the [IALink Interface](ialink-interface.md) for use.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b29c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="b29c3-104">Syntax</span></span>  
  
```cpp  
HRESULT Init(  
    IMetaDataDispenserEx* pDispenser,  
    IMetaDataError* pErrorHandler  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="b29c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b29c3-105">Parameters</span></span>  
 `pDispenser`  
 <span data-ttu-id="b29c3-106">메타 데이터 디스펜서에 대 한 [IMetaDataDispenserEx 인터페이스](../metadata/imetadatadispenserex-interface.md) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b29c3-106">[IMetaDataDispenserEx Interface](../metadata/imetadatadispenserex-interface.md) pointer to the metadata dispenser.</span></span>  
  
 `pErrorHandler`  
 <span data-ttu-id="b29c3-107">선택적 오류 처리 인터페이스에 대 한 [IMetaDataError 인터페이스](../metadata/imetadataerror-interface.md) 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="b29c3-107">[IMetaDataError Interface](../metadata/imetadataerror-interface.md) pointer to an optional error handling interface.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b29c3-108">반환 값</span><span class="sxs-lookup"><span data-stu-id="b29c3-108">Return Value</span></span>  
 <span data-ttu-id="b29c3-109">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="b29c3-109">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b29c3-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b29c3-110">Requirements</span></span>  
 <span data-ttu-id="b29c3-111">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="b29c3-111">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b29c3-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b29c3-112">See also</span></span>

- [<span data-ttu-id="b29c3-113">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b29c3-113">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="b29c3-114">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="b29c3-114">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="b29c3-115">ALink API</span><span class="sxs-lookup"><span data-stu-id="b29c3-115">ALink API</span></span>](index.md)
