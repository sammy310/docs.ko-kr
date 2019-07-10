---
title: ImportTypes 메서드
ms.date: 03/30/2017
api_name:
- IALink.ImportTypes
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes
helpviewer_keywords:
- ImportTypes method
ms.assetid: 351d4b4c-c939-486d-9471-51914a55f471
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9876e3ba5ea67442714c2d00b1901c25e54494f2
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67741631"
---
# <a name="importtypes-method"></a><span data-ttu-id="9ff14-102">ImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="9ff14-102">ImportTypes Method</span></span>
<span data-ttu-id="9ff14-103">시작을 통해 가져온 각 범위에서 형식을 가져올 [ImportFile 메서드](../../../../docs/framework/unmanaged-api/alink/importfile-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-103">Initiates the importing of types from each scope imported via [ImportFile Method](../../../../docs/framework/unmanaged-api/alink/importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ff14-104">구문</span><span class="sxs-lookup"><span data-stu-id="9ff14-104">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ff14-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9ff14-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="9ff14-106">가져올 대상 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="9ff14-107">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="9ff14-108">가져오려는 0부터 시작 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="9ff14-109">이 범위에서 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="9ff14-110">필요에 따라 받는 [IMetaDataImport 인터페이스](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-110">Optionally receives [IMetaDataImport Interface](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="9ff14-111">필요에 따라 지정 된 범위에서 형식 개수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ff14-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="9ff14-112">Return Value</span></span>  
 <span data-ttu-id="9ff14-113">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="9ff14-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ff14-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9ff14-114">Requirements</span></span>  
 <span data-ttu-id="9ff14-115">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="9ff14-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9ff14-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="9ff14-116">See also</span></span>

- [<span data-ttu-id="9ff14-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ff14-117">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="9ff14-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9ff14-118">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="9ff14-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="9ff14-119">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
