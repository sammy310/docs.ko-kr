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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3a0e42e9ffb99896bdd09dbbab65eafb40cafff
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70777214"
---
# <a name="getscope-method"></a><span data-ttu-id="c9c0f-102">GetScope 메서드</span><span class="sxs-lookup"><span data-stu-id="c9c0f-102">GetScope Method</span></span>
<span data-ttu-id="c9c0f-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c9c0f-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c9c0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="c9c0f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="c9c0f-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c9c0f-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c9c0f-106">가져올 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c9c0f-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c9c0f-107">가져올 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c9c0f-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="c9c0f-108">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="c9c0f-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="c9c0f-109">범위에 대 한 [IMetaDataImport 인터페이스](../metadata/imetadataimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9c0f-109">Receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c9c0f-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c9c0f-110">Return Value</span></span>  
 <span data-ttu-id="c9c0f-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c9c0f-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c9c0f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c9c0f-112">Requirements</span></span>  
 <span data-ttu-id="c9c0f-113">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="c9c0f-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c9c0f-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c9c0f-114">See also</span></span>

- [<span data-ttu-id="c9c0f-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9c0f-115">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="c9c0f-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c9c0f-116">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="c9c0f-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="c9c0f-117">ALink API</span></span>](index.md)
