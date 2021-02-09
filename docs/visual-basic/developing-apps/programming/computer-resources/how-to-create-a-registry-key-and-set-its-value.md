---
description: '자세한 정보: 방법: Visual Basic에서 레지스트리 키 만들기 및 해당 값 설정'
title: '방법: 레지스트리 키 만들기 및 값 설정'
ms.date: 07/20/2015
f1_keywords:
- RegistryKey.CreateSubKey
- RegistryKey.SetValue
helpviewer_keywords:
- registry keys [Visual Basic], creating
- registry [Visual Basic], adding values
- registry [Visual Basic], adding keys
- registry keys [Visual Basic], setting values
- examples [Visual Basic], registry
ms.assetid: d3e40f74-c283-480c-ab18-e5e9052cd814
ms.openlocfilehash: 73a6f5b2a092bb05df704fe6b9954ccbe13b5d90
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99797733"
---
# <a name="how-to-create-a-registry-key-and-set-its-value-in-visual-basic"></a><span data-ttu-id="e5e62-103">방법: Visual Basic에서 레지스트리 키 만들기 및 값 설정</span><span class="sxs-lookup"><span data-stu-id="e5e62-103">How to: Create a Registry Key and Set Its Value in Visual Basic</span></span>

<span data-ttu-id="e5e62-104">`My.Computer.Registry` 개체의 `CreateSubKey` 메서드를 사용하여 레지스트리 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-104">The `CreateSubKey` method of the `My.Computer.Registry` object can be used to create a registry key.</span></span>

## <a name="procedure"></a><span data-ttu-id="e5e62-105">프로시저</span><span class="sxs-lookup"><span data-stu-id="e5e62-105">Procedure</span></span>

### <a name="to-create-a-registry-key"></a><span data-ttu-id="e5e62-106">레지스트리 키를 만들려면</span><span class="sxs-lookup"><span data-stu-id="e5e62-106">To create a registry key</span></span>

- <span data-ttu-id="e5e62-107">키를 배치할 하이브와 키 이름을 지정하여 `CreateSubKey` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-107">Use the `CreateSubKey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="e5e62-108">`Subkey` 매개 변수는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-108">The parameter `Subkey` is not case-sensitive.</span></span> <span data-ttu-id="e5e62-109">이 예제에서는 HKEY_CURRENT_USER 아래에 레지스트리 키 `MyTestKey`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-109">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

### <a name="to-create-a-registry-key-and-set-a-value-in-it"></a><span data-ttu-id="e5e62-110">레지스트리 키를 만들고 키에 값을 설정하려면</span><span class="sxs-lookup"><span data-stu-id="e5e62-110">To create a registry key and set a value in it</span></span>

1. <span data-ttu-id="e5e62-111">키를 배치할 하이브와 키 이름을 지정하여 `CreateSubkey` 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-111">Use the `CreateSubkey` method, specifying which hive to place the key under as well as the name of the key.</span></span> <span data-ttu-id="e5e62-112">이 예제에서는 HKEY_CURRENT_USER 아래에 레지스트리 키 `MyTestKey`를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-112">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER.</span></span>

    [!code-vb[VbResourceTasks#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#17)]

2. <span data-ttu-id="e5e62-113">`SetValue` 메서드를 사용하여 값을 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-113">Set the value with the `SetValue` method.</span></span> <span data-ttu-id="e5e62-114">이 예제에서는 문자열 값</span><span class="sxs-lookup"><span data-stu-id="e5e62-114">This example sets the string value.</span></span> <span data-ttu-id="e5e62-115">"MyTestKeyValue"를 "This is a test value"로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-115">"MyTestKeyValue" to "This is a test value".</span></span>

    [!code-vb[VbResourceTasks#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#14)]

## <a name="example"></a><span data-ttu-id="e5e62-116">예제</span><span class="sxs-lookup"><span data-stu-id="e5e62-116">Example</span></span>

<span data-ttu-id="e5e62-117">이 예제에서는 HKEY_CURRENT_USER 아래에 레지스트리 키 `MyTestKey`를 만든 다음 문자열 값 `MyTestKeyValue`를 `This is a test value`로 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-117">This example creates the registry key `MyTestKey` under HKEY_CURRENT_USER and then sets the string value `MyTestKeyValue` to `This is a test value`.</span></span>

[!code-vb[VbResourceTasks#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbResourceTasks/VB/Class1.vb#15)]

## <a name="robust-programming"></a><span data-ttu-id="e5e62-118">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="e5e62-118">Robust Programming</span></span>

<span data-ttu-id="e5e62-119">레지스트리 구조를 검사하여 키에 적합한 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-119">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="e5e62-120">예를 들어 현재 사용자의 HKEY_CURRENT_USER\Software 키를 열고 회사 이름으로 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-120">For example, you may want to open the HKEY_CURRENT_USER\Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="e5e62-121">그런 다음 회사 키에 레지스트리 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-121">Then add the registry values to your company's key.</span></span>

<span data-ttu-id="e5e62-122">웹 애플리케이션에서 레지스트리를 읽는 경우 현재 사용자는 웹 애플리케이션에 구현된 인증 및 가장에 따라 결정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-122">When reading the registry from a Web application, the current user depends on the authentication and impersonation implemented in the Web application.</span></span>

<span data-ttu-id="e5e62-123">로컬 컴퓨터(<xref:Microsoft.Win32.Registry.LocalMachine>)보다 사용자 폴더(<xref:Microsoft.Win32.Registry.CurrentUser>)에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-123">It is more secure to write data to the user folder (<xref:Microsoft.Win32.Registry.CurrentUser>) rather than to the local computer (<xref:Microsoft.Win32.Registry.LocalMachine>).</span></span>

<span data-ttu-id="e5e62-124">레지스트리 값을 만들 때 해당 값이 이미 있는 경우 수행할 작업을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-124">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="e5e62-125">다른 악성 프로세스에서 값을 이미 만들고 액세스했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-125">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="e5e62-126">레지스트리 값에 데이터를 넣으면 다른 프로세스에서 해당 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-126">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="e5e62-127">이를 방지하려면 <xref:Microsoft.Win32.RegistryKey.GetValue%2A> 메서드를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-127">To prevent this, use the <xref:Microsoft.Win32.RegistryKey.GetValue%2A> method.</span></span> <span data-ttu-id="e5e62-128">키가 아직 없는 경우 `Nothing`이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-128">It returns `Nothing` if the key does not already exist.</span></span>

<span data-ttu-id="e5e62-129">레지스트리 키가 ACL(액세스 제어 목록)로 보호된 경우에도 비밀(예: 암호)을 레지스트리에 일반 텍스트로 저장하는 것은 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-129">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by ACLs (Access Control Lists).</span></span>

<span data-ttu-id="e5e62-130">다음 조건에서 예외가 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-130">The following conditions may cause an exception:</span></span>

- <span data-ttu-id="e5e62-131">키의 이름이 `Nothing`인 경우(<xref:System.ArgumentNullException>)</span><span class="sxs-lookup"><span data-stu-id="e5e62-131">The name of the key is `Nothing` (<xref:System.ArgumentNullException>).</span></span>

- <span data-ttu-id="e5e62-132">사용자에게 레지스트리 키를 만들 수 있는 권한이 없는 경우(<xref:System.Security.SecurityException>)</span><span class="sxs-lookup"><span data-stu-id="e5e62-132">The user does not have permissions to create registry keys (<xref:System.Security.SecurityException>).</span></span>

- <span data-ttu-id="e5e62-133">키 이름이 255자 제한을 초과하는 경우(<xref:System.ArgumentException>)</span><span class="sxs-lookup"><span data-stu-id="e5e62-133">The key name exceeds the 255-character limit (<xref:System.ArgumentException>).</span></span>

- <span data-ttu-id="e5e62-134">키가 닫힌 경우(<xref:System.IO.IOException>)</span><span class="sxs-lookup"><span data-stu-id="e5e62-134">The key is closed (<xref:System.IO.IOException>).</span></span>

- <span data-ttu-id="e5e62-135">레지스트리 키가 읽기 전용인 경우(<xref:System.UnauthorizedAccessException>)</span><span class="sxs-lookup"><span data-stu-id="e5e62-135">The registry key is read-only (<xref:System.UnauthorizedAccessException>).</span></span>

## <a name="net-framework-security"></a><span data-ttu-id="e5e62-136">.NET Framework 보안</span><span class="sxs-lookup"><span data-stu-id="e5e62-136">.NET Framework Security</span></span>

<span data-ttu-id="e5e62-137">이 프로세스를 실행하려면 어셈블리에 <xref:System.Security.Permissions.RegistryPermission> 클래스에서 부여한 권한 수준이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-137">To run this process, your assembly requires a privilege level granted by the <xref:System.Security.Permissions.RegistryPermission> class.</span></span> <span data-ttu-id="e5e62-138">부분 신뢰 컨텍스트에서 실행하는 경우 프로세스가 권한 부족으로 인해 예외를 throw할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-138">If you are running in a partial-trust context, the process might throw an exception due to insufficient privileges.</span></span> <span data-ttu-id="e5e62-139">마찬가지로, 사용자에게 설정을 만들거나 쓸 수 있는 올바른 ACL이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-139">Similarly, the user must have the correct ACLs for creating or writing to settings.</span></span> <span data-ttu-id="e5e62-140">예를 들어 코드 액세스 보안 권한이 있는 로컬 애플리케이션에는 운영 체제 권한이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e5e62-140">For example, a local application that has the code access security permission might not have operating system permission.</span></span> <span data-ttu-id="e5e62-141">자세한 내용은 [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="e5e62-141">For more information, see [Code Access Security Basics](../../../../framework/misc/code-access-security-basics.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e5e62-142">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e5e62-142">See also</span></span>

- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy>
- <xref:Microsoft.VisualBasic.MyServices.RegistryProxy.CurrentUser%2A>
- <xref:Microsoft.Win32.RegistryKey.CreateSubKey%2A>
- [<span data-ttu-id="e5e62-143">레지스트리 읽기 및 쓰기</span><span class="sxs-lookup"><span data-stu-id="e5e62-143">Reading from and Writing to the Registry</span></span>](reading-from-and-writing-to-the-registry.md)
- [<span data-ttu-id="e5e62-144">코드 액세스 보안 기본 사항</span><span class="sxs-lookup"><span data-stu-id="e5e62-144">Code Access Security Basics</span></span>](../../../../framework/misc/code-access-security-basics.md)
