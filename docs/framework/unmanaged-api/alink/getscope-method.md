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
ms.openlocfilehash: c8de6c745b1d32c3d98f1b54e822ab084f0574b2
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57486201"
---
# <a name="getscope-method"></a><span data-ttu-id="ae240-102">GetScope 메서드</span><span class="sxs-lookup"><span data-stu-id="ae240-102">GetScope Method</span></span>
<span data-ttu-id="ae240-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ae240-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ae240-104">구문</span><span class="sxs-lookup"><span data-stu-id="ae240-104">Syntax</span></span>  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="ae240-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ae240-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="ae240-106">가져올 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae240-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="ae240-107">가져올 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="ae240-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="ae240-108">가져오려는 0부터 시작 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="ae240-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="ae240-109">수신 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="ae240-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ae240-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="ae240-110">Return Value</span></span>  
 <span data-ttu-id="ae240-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="ae240-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ae240-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ae240-112">Requirements</span></span>  
 <span data-ttu-id="ae240-113">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="ae240-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ae240-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="ae240-114">See also</span></span>
- [<span data-ttu-id="ae240-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae240-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="ae240-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ae240-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="ae240-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="ae240-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
