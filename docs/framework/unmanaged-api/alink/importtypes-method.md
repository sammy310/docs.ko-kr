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
ms.openlocfilehash: 76d2b163f959111923bffb1348890f6fbb29828e
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445685"
---
# <a name="importtypes-method"></a><span data-ttu-id="0a961-102">ImportTypes 메서드</span><span class="sxs-lookup"><span data-stu-id="0a961-102">ImportTypes Method</span></span>
<span data-ttu-id="0a961-103">[Importfile 메서드](importfile-method.md)를 통해 가져온 각 범위에서 형식의 가져오기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-103">Initiates the importing of types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a961-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a961-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="0a961-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="0a961-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="0a961-106">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-106">ID of the assembly to import to.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="0a961-107">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-107">ID of the file to import from.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="0a961-108">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-108">Zero-based scope to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="0a961-109">이 범위에 있는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-109">Receives enumerator handle for the types in this scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="0a961-110">선택적으로 [IMetaDataImport 인터페이스](../metadata/imetadataimport-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-110">Optionally receives [IMetaDataImport Interface](../metadata/imetadataimport-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="0a961-111">지정 된 범위에서 필요에 따라 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-111">Optionally receives count of types in the indicated scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0a961-112">반환 값</span><span class="sxs-lookup"><span data-stu-id="0a961-112">Return Value</span></span>  
 <span data-ttu-id="0a961-113">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a961-113">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a961-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="0a961-114">Requirements</span></span>  
 <span data-ttu-id="0a961-115">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="0a961-115">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a961-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a961-116">See also</span></span>

- [<span data-ttu-id="0a961-117">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a961-117">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="0a961-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="0a961-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="0a961-119">ALink API</span><span class="sxs-lookup"><span data-stu-id="0a961-119">ALink API</span></span>](index.md)
