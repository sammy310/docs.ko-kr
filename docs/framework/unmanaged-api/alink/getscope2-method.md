---
title: GetScope2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.GetScope2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope2
helpviewer_keywords:
- GetScope2 method
ms.assetid: 49435665-6f5a-4acd-9034-8c9244a04a63
topic_type:
- apiref
ms.openlocfilehash: e8c6fd7dca13afe7504e447caca9a217c8136c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95684527"
---
# <a name="getscope2-method"></a><span data-ttu-id="9226b-102">GetScope2 메서드</span><span class="sxs-lookup"><span data-stu-id="9226b-102">GetScope2 Method</span></span>

<span data-ttu-id="9226b-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9226b-104">구문</span><span class="sxs-lookup"><span data-stu-id="9226b-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;
```  
  
## <a name="parameters"></a><span data-ttu-id="9226b-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9226b-105">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="9226b-106">대상 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9226b-107">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9226b-108">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9226b-109">표시 된 범위에 대 한 [IMetaDataImport2 interface](../metadata/imetadataimport2-interface.md) 인터페이스에 대 한 포인터를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-109">Receives pointer to [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9226b-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="9226b-110">Return Value</span></span>  

 <span data-ttu-id="9226b-111">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9226b-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9226b-112">Requirements</span></span>  

 <span data-ttu-id="9226b-113">Alink가 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="9226b-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9226b-114">참조</span><span class="sxs-lookup"><span data-stu-id="9226b-114">See also</span></span>

- [<span data-ttu-id="9226b-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9226b-115">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="9226b-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9226b-116">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="9226b-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="9226b-117">ALink API</span></span>](index.md)
