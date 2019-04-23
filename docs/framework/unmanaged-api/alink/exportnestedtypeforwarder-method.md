---
title: ExportNestedTypeForwarder 메서드
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 050ed0bbd4da38bede5a56ff95d0243f5f3cf1da
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59220086"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="3df90-102">ExportNestedTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="3df90-102">ExportNestedTypeForwarder Method</span></span>
<span data-ttu-id="3df90-103">중첩 된 형식에 대 한 형식 전달 자가 지정된 된 어셈블리의 type 테이블에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-103">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df90-104">구문</span><span class="sxs-lookup"><span data-stu-id="3df90-104">Syntax</span></span>  
  
```  
HRESULT ExportNestedTypeForwarder(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;  
```  
  
## <a name="parameters"></a><span data-ttu-id="3df90-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3df90-105">Parameters</span></span>  
 `AssemblyID`  
 <span data-ttu-id="3df90-106">내보내는 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-106">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="3df90-107">파일 형식을 정의 하는 파일의 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-107">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="3df90-108">토큰 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-108">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="3df90-109">부모 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-109">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="3df90-110">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-110">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="3df90-111">`ComType` 와 같은 플래그 `tdPublic` 또는 `tdNested`합니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-111">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="3df90-112">내보내기 형식의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-112">Receives token of export type.</span></span> <span data-ttu-id="3df90-113">이 중첩 된 형식을 내보내는에 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-113">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3df90-114">반환 값</span><span class="sxs-lookup"><span data-stu-id="3df90-114">Return Value</span></span>  
 <span data-ttu-id="3df90-115">메서드가 성공 하면 S_OK를 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="3df90-115">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3df90-116">요구 사항</span><span class="sxs-lookup"><span data-stu-id="3df90-116">Requirements</span></span>  
 <span data-ttu-id="3df90-117">Alink.h 필요</span><span class="sxs-lookup"><span data-stu-id="3df90-117">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df90-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="3df90-118">See also</span></span>

- [<span data-ttu-id="3df90-119">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3df90-119">IALink Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [<span data-ttu-id="3df90-120">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="3df90-120">IALink2 Interface</span></span>](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [<span data-ttu-id="3df90-121">ALink API</span><span class="sxs-lookup"><span data-stu-id="3df90-121">ALink API</span></span>](../../../../docs/framework/unmanaged-api/alink/index.md)
