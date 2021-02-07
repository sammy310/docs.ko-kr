---
description: '자세히 알아보기: GetScope 메서드'
title: GetScope 메서드
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
ms.openlocfilehash: cdebda457573e70755b49798ae86eae8f076216b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718361"
---
# <a name="getscope-method"></a><span data-ttu-id="4f633-103">GetScope 메서드</span><span class="sxs-lookup"><span data-stu-id="4f633-103">GetScope Method</span></span>

<span data-ttu-id="4f633-104">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4f633-104">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4f633-105">구문</span><span class="sxs-lookup"><span data-stu-id="4f633-105">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="4f633-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4f633-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="4f633-107">가져올 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4f633-107">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="4f633-108">가져올 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="4f633-108">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="4f633-109">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="4f633-109">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="4f633-110">범위에 대 한 [IMetaDataImport 인터페이스](../metadata/imetadataimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f633-110">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4f633-111">Return Value</span><span class="sxs-lookup"><span data-stu-id="4f633-111">Return Value</span></span>  

 <span data-ttu-id="4f633-112">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="4f633-112">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4f633-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4f633-113">Requirements</span></span>  

 <span data-ttu-id="4f633-114">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="4f633-114">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f633-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="4f633-115">See also</span></span>

- [<span data-ttu-id="4f633-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f633-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="4f633-117">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="4f633-117">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="4f633-118">ALink API</span><span class="sxs-lookup"><span data-stu-id="4f633-118">ALink API</span></span>](index.md)
