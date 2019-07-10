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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 0c0abc63610f3f1ed6e8a556c44ee15edc1ea20b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741834"
---
# <a name="getscope2-method"></a><span data-ttu-id="c61c3-102">GetScope2 메서드</span><span class="sxs-lookup"><span data-stu-id="c61c3-102">GetScope2 Method</span></span>
<span data-ttu-id="c61c3-103">가져오기 범위를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-103">Gets an import scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c61c3-104">구문</span><span class="sxs-lookup"><span data-stu-id="c61c3-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScope2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport2** ppImportScope  
) PURE;   
```  
  
## <a name="parameters"></a><span data-ttu-id="c61c3-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c61c3-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="c61c3-106">대상 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-106">ID of target assembly.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="c61c3-107">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-107">ID of file from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="c61c3-108">가져오려는 0부터 시작 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-108">Zero-based scope to import.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="c61c3-109">에 대 한 포인터를 받는 [IMetaDataImport2 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) 표시 된 범위에 대 한 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-109">Receives pointer to [IMetaDataImport2 Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md) interface for indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c61c3-110">반환 값</span><span class="sxs-lookup"><span data-stu-id="c61c3-110">Return Value</span></span>  
 <span data-ttu-id="c61c3-111">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-111">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c61c3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c61c3-112">Requirements</span></span>  
 <span data-ttu-id="c61c3-113">Alink.h가 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="c61c3-113">Requires alink.h.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c61c3-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="c61c3-114">See also</span></span>

- [<span data-ttu-id="c61c3-115">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c61c3-115">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="c61c3-116">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="c61c3-116">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="c61c3-117">ALink API</span><span class="sxs-lookup"><span data-stu-id="c61c3-117">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
