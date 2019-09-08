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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: ce09eca30e1edb9e1afc02216a07955a5fed4fd2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/07/2019
ms.locfileid: "70787261"
---
# <a name="importtypes2-method"></a><span data-ttu-id="222de-102">ImportTypes2 메서드</span><span class="sxs-lookup"><span data-stu-id="222de-102">ImportTypes2 Method</span></span>
<span data-ttu-id="222de-103">형식의 가져오기를 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="222de-103">Initiates the import of types.</span></span> <span data-ttu-id="222de-104">[Importfile 메서드](importfile-method.md)를 통해 가져온 각 범위에서 형식 가져오기를 시작 하려면이 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="222de-104">Call this method to begin importing types from each scope imported via [ImportFile Method](importfile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="222de-105">구문</span><span class="sxs-lookup"><span data-stu-id="222de-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="222de-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="222de-106">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="222de-107">가져올 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="222de-107">ID of assembly into which to import.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="222de-108">가져올 파일의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="222de-108">ID of file to from which to import.</span></span>  
  
 `dwScope`  
 <span data-ttu-id="222de-109">가져올 범위 (0부터 시작)입니다.</span><span class="sxs-lookup"><span data-stu-id="222de-109">Zero-based scope from which to import.</span></span>  
  
 `phEnum`  
 <span data-ttu-id="222de-110">지정 된 범위에 있는 형식에 대 한 열거자 핸들을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="222de-110">Receives enumerator handle for the types in the given scope.</span></span>  
  
 `ppImportScope`  
 <span data-ttu-id="222de-111">선택적으로 [IMetaDataImport2 인터페이스](../metadata/imetadataimport2-interface.md) 인터페이스를 수신 합니다.</span><span class="sxs-lookup"><span data-stu-id="222de-111">Optionally receives [IMetaDataImport2 Interface](../metadata/imetadataimport2-interface.md) interface.</span></span>  
  
 `pdwCountOfTypes`  
 <span data-ttu-id="222de-112">선택적으로 지정 된 범위에 있는 형식의 수를 받습니다.</span><span class="sxs-lookup"><span data-stu-id="222de-112">Optionally receives count of types in the specified scope.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="222de-113">반환 값</span><span class="sxs-lookup"><span data-stu-id="222de-113">Return Value</span></span>  
 <span data-ttu-id="222de-114">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="222de-114">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="222de-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="222de-115">Requirements</span></span>  
 <span data-ttu-id="222de-116">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="222de-116">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="222de-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="222de-117">See also</span></span>

- [<span data-ttu-id="222de-118">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="222de-118">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="222de-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="222de-119">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="222de-120">ALink API</span><span class="sxs-lookup"><span data-stu-id="222de-120">ALink API</span></span>](index.md)
