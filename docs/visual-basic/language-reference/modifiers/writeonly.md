---
title: WriteOnly
ms.date: 07/20/2015
f1_keywords:
- WriteOnly
- vb.WriteOnly
helpviewer_keywords:
- write-only properties
- WriteOnly keyword [Visual Basic]
- sensitive data, protecting
- properties [Visual Basic], write-only
- sensitive data
ms.assetid: 488d2899-b09f-4cee-92f0-6f9f9fc4f944
ms.openlocfilehash: 847617ea6534089857a759fbea3bb16a3a5a36a1
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74344197"
---
# <a name="writeonly-visual-basic"></a><span data-ttu-id="18d13-102">WriteOnly(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="18d13-102">WriteOnly (Visual Basic)</span></span>
<span data-ttu-id="18d13-103">속성을 쓸 수 있지만 읽을 수 없도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-103">Specifies that a property can be written but not read.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="18d13-104">주의</span><span class="sxs-lookup"><span data-stu-id="18d13-104">Remarks</span></span>  
  
## <a name="rules"></a><span data-ttu-id="18d13-105">규칙</span><span class="sxs-lookup"><span data-stu-id="18d13-105">Rules</span></span>  
 <span data-ttu-id="18d13-106">**선언 컨텍스트입니다.**</span><span class="sxs-lookup"><span data-stu-id="18d13-106">**Declaration Context.**</span></span> <span data-ttu-id="18d13-107">`WriteOnly`는 모듈 수준에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-107">You can use `WriteOnly` only at module level.</span></span> <span data-ttu-id="18d13-108">즉, `WriteOnly` 속성의 선언 컨텍스트는 클래스, 구조체 또는 모듈 이어야 하며 소스 파일, 네임 스페이스 또는 프로시저일 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-108">This means the declaration context for a `WriteOnly` property must be a class, structure, or module, and cannot be a source file, namespace, or procedure.</span></span>  
  
 <span data-ttu-id="18d13-109">속성은 변수를 제외 하 고 `WriteOnly`선언할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-109">You can declare a property as `WriteOnly`, but not a variable.</span></span>  
  
## <a name="when-to-use-writeonly"></a><span data-ttu-id="18d13-110">WriteOnly를 사용 하는 경우</span><span class="sxs-lookup"><span data-stu-id="18d13-110">When to Use WriteOnly</span></span>  
 <span data-ttu-id="18d13-111">소비 하는 코드에서 값을 설정할 수 있지만 해당 값을 검색 하지 않으려는 경우가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-111">Sometimes you want the consuming code to be able to set a value but not discover what it is.</span></span> <span data-ttu-id="18d13-112">예를 들어 소셜 등록 번호 또는 암호와 같은 중요 한 데이터는 해당 데이터를 설정 하지 않은 구성 요소에의 한 액세스 로부터 보호 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-112">For example, sensitive data, such as a social registration number or a password, needs to be protected from access by any component that did not set it.</span></span> <span data-ttu-id="18d13-113">이 경우 `WriteOnly` 속성을 사용 하 여 값을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-113">In these cases, you can use a `WriteOnly` property to set the value.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="18d13-114">`WriteOnly` 속성을 정의 하 고 사용 하는 경우 다음과 같은 추가 보호 조치를 고려 하십시오.</span><span class="sxs-lookup"><span data-stu-id="18d13-114">When you define and use a `WriteOnly` property, consider the following additional protective measures:</span></span>  
  
- <span data-ttu-id="18d13-115">**덮어쓰지.**</span><span class="sxs-lookup"><span data-stu-id="18d13-115">**Overriding.**</span></span> <span data-ttu-id="18d13-116">속성이 클래스의 멤버 이면 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)에 대 한 기본값을 허용 하 고 `Overridable` 또는 `MustOverride`을 선언 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-116">If the property is a member of a class, allow it to default to [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md), and do not declare it `Overridable` or `MustOverride`.</span></span> <span data-ttu-id="18d13-117">이렇게 하면 파생 클래스가 재정의를 통해 원치 않는 액세스를 수행할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-117">This prevents a derived class from making undesired access through an override.</span></span>  
  
- <span data-ttu-id="18d13-118">**액세스 수준입니다.**</span><span class="sxs-lookup"><span data-stu-id="18d13-118">**Access Level.**</span></span> <span data-ttu-id="18d13-119">하나 이상의 변수에 속성의 중요 한 데이터를 저장 하는 경우 다른 코드에서 액세스할 수 없도록 [Private](../../../visual-basic/language-reference/modifiers/private.md) 을 선언 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-119">If you hold the property's sensitive data in one or more variables, declare them [Private](../../../visual-basic/language-reference/modifiers/private.md) so that no other code can access them.</span></span>  
  
- <span data-ttu-id="18d13-120">**암호화.**</span><span class="sxs-lookup"><span data-stu-id="18d13-120">**Encryption.**</span></span> <span data-ttu-id="18d13-121">모든 중요 한 데이터를 일반 텍스트가 아닌 암호화 된 형식으로 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-121">Store all sensitive data in encrypted form rather than in plain text.</span></span> <span data-ttu-id="18d13-122">악의적인 코드가 해당 메모리 영역에 대 한 액세스 권한을 얻으면 데이터를 사용 하는 것이 더 어려워집니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-122">If malicious code somehow gains access to that area of memory, it is more difficult to make use of the data.</span></span> <span data-ttu-id="18d13-123">암호화는 중요 한 데이터를 직렬화 해야 하는 경우에도 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-123">Encryption is also useful if it is necessary to serialize the sensitive data.</span></span>  
  
- <span data-ttu-id="18d13-124">**다시 설정.**</span><span class="sxs-lookup"><span data-stu-id="18d13-124">**Resetting.**</span></span> <span data-ttu-id="18d13-125">속성을 정의 하는 클래스, 구조체 또는 모듈을 종료 하는 경우 중요 한 데이터를 기본값으로 다시 설정 하거나 다른 의미 없는 값으로 다시 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-125">When the class, structure, or module defining the property is being terminated, reset the sensitive data to default values or to other meaningless values.</span></span> <span data-ttu-id="18d13-126">이는 일반 액세스를 위해 메모리 영역을 해제할 때 추가 보호 기능을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-126">This gives extra protection when that area of memory is freed for general access.</span></span>  
  
- <span data-ttu-id="18d13-127">**지.**</span><span class="sxs-lookup"><span data-stu-id="18d13-127">**Persistence.**</span></span> <span data-ttu-id="18d13-128">중요 한 데이터 (예: 디스크를 사용 하지 않는 경우)를 유지 하지 마세요.</span><span class="sxs-lookup"><span data-stu-id="18d13-128">Do not persist any sensitive data, for example on disk, if you can avoid it.</span></span> <span data-ttu-id="18d13-129">또한 중요 한 데이터를 클립보드에 쓰지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-129">Also, do not write any sensitive data to the Clipboard.</span></span>  
  
 <span data-ttu-id="18d13-130">이 컨텍스트에서는 `WriteOnly` 한정자를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="18d13-130">The `WriteOnly` modifier can be used in this context:</span></span>  
  
 [<span data-ttu-id="18d13-131">Property 문</span><span class="sxs-lookup"><span data-stu-id="18d13-131">Property Statement</span></span>](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## <a name="see-also"></a><span data-ttu-id="18d13-132">참고 항목</span><span class="sxs-lookup"><span data-stu-id="18d13-132">See also</span></span>

- [<span data-ttu-id="18d13-133">ReadOnly</span><span class="sxs-lookup"><span data-stu-id="18d13-133">ReadOnly</span></span>](../../../visual-basic/language-reference/modifiers/readonly.md)
- [<span data-ttu-id="18d13-134">Private</span><span class="sxs-lookup"><span data-stu-id="18d13-134">Private</span></span>](../../../visual-basic/language-reference/modifiers/private.md)
- [<span data-ttu-id="18d13-135">키워드</span><span class="sxs-lookup"><span data-stu-id="18d13-135">Keywords</span></span>](../../../visual-basic/language-reference/keywords/index.md)
