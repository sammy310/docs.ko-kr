---
title: ImportTypes2 메서드
ms.date: 03/30/2017
api_name:
- IALink2.ImportTypes2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportTypes2
helpviewer_keywords:
- ImportTypes2 method
ms.assetid: 32f3ba58-9695-41e9-ba58-fd19e45ed396
topic_type:
- apiref
ms.openlocfilehash: 2ec7708edd86b9f2656d0eee434992c3b73200ca
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95705048"
---
# <a name="importtypes2-method"></a><span data-ttu-id="3227c-102">ImportTypes2 메서드</span><span class="sxs-lookup"><span data-stu-id="3227c-102">ImportTypes2 Method</span></span>

<span data-ttu-id="3227c-103">형식의 가져오기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-103">Initiates the import of types.</span></span> <span data-ttu-id="3227c-104">[Importfile 메서드](importfile-method.md)를 통해 가져온 각 범위에서 형식 가져오기를 시작 하려면이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3227c-105">구문</span><span class="sxs-lookup"><span data-stu-id="3227c-105">Syntax</span></span>  
  
```cpp  
HRESULT ImportTypes2(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    HALINKENUM* phEnum,  
    IMetaDataImport2** ppImportScope,  
    DWORD* pdwCountOfTypes  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3227c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3227c-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="3227c-107">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3227c-108">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="3227c-109">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="3227c-110">지정 된 범위에 있는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="3227c-111">선택적으로 [IMetaDataImport2 인터페이스](../metadata/imetadataimport2-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="3227c-112">선택적으로 지정 된 범위에 있는 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3227c-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="3227c-113">Return Value</span></span>  

 <span data-ttu-id="3227c-114">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3227c-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3227c-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3227c-115">Requirements</span></span>  

 <span data-ttu-id="3227c-116">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="3227c-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3227c-117">참조</span><span class="sxs-lookup"><span data-stu-id="3227c-117">See also</span></span>

- [<span data-ttu-id="3227c-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3227c-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="3227c-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3227c-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="3227c-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="3227c-120">ALink API</span></span>](index.md)
