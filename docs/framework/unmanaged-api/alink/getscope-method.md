---
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
ms.openlocfilehash: fd5ae6ef40cb171c33132df0f640acbef96d69b5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684678"
---
# <a name="getscope-method"></a><span data-ttu-id="e0947-102">GetScope 메서드</span><span class="sxs-lookup"><span data-stu-id="e0947-102">GetScope Method</span></span>

<span data-ttu-id="e0947-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e0947-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e0947-104">구문</span><span class="sxs-lookup"><span data-stu-id="e0947-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="e0947-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e0947-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="e0947-106">가져올 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e0947-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="e0947-107">가져올 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="e0947-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="e0947-108">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="e0947-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="e0947-109">범위에 대 한 [IMetaDataImport 인터페이스](../metadata/imetadataimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0947-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e0947-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="e0947-110">Return Value</span></span>  

 <span data-ttu-id="e0947-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="e0947-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e0947-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e0947-112">Requirements</span></span>  

 <span data-ttu-id="e0947-113">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="e0947-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e0947-114">참조</span><span class="sxs-lookup"><span data-stu-id="e0947-114">See also</span></span>

- [<span data-ttu-id="e0947-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0947-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="e0947-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="e0947-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="e0947-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="e0947-117">ALink API</span></span>](index.md)
