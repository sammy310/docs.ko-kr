---
description: '자세히 알아보기: ExportNestedTypeForwarder 메서드'
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
ms.openlocfilehash: fd791e3fea76338f191fcf924d56720d257d2e8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638108"
---
# <a name="exportnestedtypeforwarder-method"></a><span data-ttu-id="2c9f0-103">ExportNestedTypeForwarder 메서드</span><span class="sxs-lookup"><span data-stu-id="2c9f0-103">ExportNestedTypeForwarder Method</span></span>

<span data-ttu-id="2c9f0-104">중첩 된 형식의 형식 전달자를 지정 된 어셈블리의 형식 테이블에 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-104">Adds a type forwarder for a nested type to the type table of the given assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c9f0-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c9f0-105">Syntax</span></span>  
  
```cpp  
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
  
## <a name="parameters"></a><span data-ttu-id="2c9f0-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c9f0-106">Parameters</span></span>  

 `AssemblyID`  
 <span data-ttu-id="2c9f0-107">내보낼 어셈블리의 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-107">ID of the assembly to export from.</span></span>  
  
 `FileToken`  
 <span data-ttu-id="2c9f0-108">형식을 정의 하는 파일의 파일 토큰 또는 어셈블리 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-108">File token or assembly ID of file that defines the type.</span></span>  
  
 `TypeToken`  
 <span data-ttu-id="2c9f0-109">형식에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-109">Token for the type.</span></span>  
  
 `ParentType`  
 <span data-ttu-id="2c9f0-110">부모 형식의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-110">Token of parent type.</span></span>  
  
 `pszTypename`  
 <span data-ttu-id="2c9f0-111">내보낼 정규화 된 형식 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-111">Fully qualified type name to export.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="2c9f0-112">`ComType` 또는와 같은 `tdPublic` 플래그 `tdNested` 입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-112">`ComType` flags such as `tdPublic` or `tdNested`.</span></span>  
  
 `pType`  
 <span data-ttu-id="2c9f0-113">내보내기 유형의 토큰을 받습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-113">Receives token of export type.</span></span> <span data-ttu-id="2c9f0-114">중첩 된 형식을 내보내는 경우에만 필요 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-114">This is necessary only for emitting nested types.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2c9f0-115">Return Value</span><span class="sxs-lookup"><span data-stu-id="2c9f0-115">Return Value</span></span>  

 <span data-ttu-id="2c9f0-116">메서드가 성공 하면 S_OK을 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9f0-116">Returns S_OK if the method succeeds.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2c9f0-117">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2c9f0-117">Requirements</span></span>  

 <span data-ttu-id="2c9f0-118">Alink 필요</span><span class="sxs-lookup"><span data-stu-id="2c9f0-118">Requires alink.h</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9f0-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c9f0-119">See also</span></span>

- [<span data-ttu-id="2c9f0-120">IALink 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c9f0-120">IALink Interface</span></span>](ialink-interface.md)
- [<span data-ttu-id="2c9f0-121">IALink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2c9f0-121">IALink2 Interface</span></span>](ialink2-interface.md)
- [<span data-ttu-id="2c9f0-122">ALink API</span><span class="sxs-lookup"><span data-stu-id="2c9f0-122">ALink API</span></span>](index.md)
