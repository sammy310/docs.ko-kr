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
ms.openlocfilehash: f3c3142ca12789b086bcd8b5a9c00c943264ae7b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741848"
---
# <a name="getscope-method"></a><span data-ttu-id="2f536-102">GetScope 메서드</span><span class="sxs-lookup"><span data-stu-id="2f536-102">GetScope Method</span></span>
<span data-ttu-id="2f536-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2f536-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2f536-104">구문</span><span class="sxs-lookup"><span data-stu-id="2f536-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="2f536-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2f536-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="2f536-106">가져올 어셈블리의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2f536-106">Unique ID of assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2f536-107">가져올 파일의 고유 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2f536-107">Unique ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="2f536-108">가져오려는 0부터 시작 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="2f536-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="2f536-109">수신 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="2f536-109">Receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface for the scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2f536-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="2f536-110">Return Value</span></span>  
 <span data-ttu-id="2f536-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2f536-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2f536-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2f536-112">Requirements</span></span>  
 <span data-ttu-id="2f536-113">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="2f536-113">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2f536-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="2f536-114">See also</span></span>

- [<span data-ttu-id="2f536-115">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f536-115">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="2f536-116">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2f536-116">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="2f536-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="2f536-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
