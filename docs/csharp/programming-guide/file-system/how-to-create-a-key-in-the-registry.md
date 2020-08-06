---
title: 레지스트리에 키를 만드는 방법 - C# 프로그래밍 가이드
description: 레지스트리에 키를 만드는 방법을 알아봅니다. 코드 예제, 컴파일 명령 및 사용 가능한 추가 리소스를 확인합니다.
ms.date: 07/20/2015
helpviewer_keywords:
- registry, adding keys and values [C#]
- registry keys, creating [C#]
- keys, creating in registry
ms.assetid: 8fa475b0-e01f-483a-9327-fd03488fdf5d
ms.openlocfilehash: 6db076bc22e098c285b74a8c10e8b5f456c2c55e
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87299983"
---
# <a name="how-to-create-a-key-in-the-registry-c-programming-guide"></a><span data-ttu-id="f14a9-104">레지스트리에 키를 만드는 방법(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f14a9-104">How to create a key in the registry (C# Programming Guide)</span></span>
<span data-ttu-id="f14a9-105">이 예제에서는 현재 사용자의 레지스트리, "Names" 키 아래에 "Name" 및 "Isabella" 값 쌍을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-105">This example adds the value pair, "Name" and "Isabella", to the current user's registry, under the key "Names".</span></span>  
  
## <a name="example"></a><span data-ttu-id="f14a9-106">예제</span><span class="sxs-lookup"><span data-stu-id="f14a9-106">Example</span></span>  
  
```csharp  
Microsoft.Win32.RegistryKey key;  
key = Microsoft.Win32.Registry.CurrentUser.CreateSubKey("Names");  
key.SetValue("Name", "Isabella");  
key.Close();  
```  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f14a9-107">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="f14a9-107">Compiling the Code</span></span>  
  
- <span data-ttu-id="f14a9-108">코드를 복사하고 콘솔 애플리케이션의 `Main` 메서드에 붙여넣습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-108">Copy the code and paste it into the `Main` method of a console application.</span></span>  
  
- <span data-ttu-id="f14a9-109">`Names` 매개 변수를 레지스트리의 HKEY_CURRENT_USER 노드 바로 아래에 있는 키 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-109">Replace the `Names` parameter with the name of a key that exists directly under the HKEY_CURRENT_USER node of the registry.</span></span>  
  
- <span data-ttu-id="f14a9-110">`Name` 매개 변수를 Names 노드 바로 아래에 있는 값 이름으로 바꿉니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-110">Replace the `Name` parameter with the name of a value that exists directly under the Names node.</span></span>  
  
## <a name="robust-programming"></a><span data-ttu-id="f14a9-111">강력한 프로그래밍</span><span class="sxs-lookup"><span data-stu-id="f14a9-111">Robust Programming</span></span>  
 <span data-ttu-id="f14a9-112">레지스트리 구조를 검사하여 키에 적합한 위치를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-112">Examine the registry structure to find a suitable location for your key.</span></span> <span data-ttu-id="f14a9-113">예를 들어 현재 사용자의 소프트웨어 키를 열고 회사 이름으로 키를 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-113">For example, you might want to open the Software key of the current user, and create a key with your company's name.</span></span> <span data-ttu-id="f14a9-114">그런 다음 회사 키에 레지스트리 값을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-114">Then add the registry values to your company's key.</span></span>  
  
 <span data-ttu-id="f14a9-115">다음 조건에서 예외가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-115">The following conditions might cause an exception:</span></span>  
  
- <span data-ttu-id="f14a9-116">키 이름이 null인 경우</span><span class="sxs-lookup"><span data-stu-id="f14a9-116">The name of the key is null.</span></span>  
  
- <span data-ttu-id="f14a9-117">사용자에게 레지스트리 키를 만들 수 있는 권한이 없는 경우</span><span class="sxs-lookup"><span data-stu-id="f14a9-117">The user does not have permissions to create registry keys.</span></span>  
  
- <span data-ttu-id="f14a9-118">키 이름이 255자 제한을 초과하는 경우</span><span class="sxs-lookup"><span data-stu-id="f14a9-118">The key name exceeds the 255-character limit.</span></span>  
  
- <span data-ttu-id="f14a9-119">키가 닫힌 경우</span><span class="sxs-lookup"><span data-stu-id="f14a9-119">The key is closed.</span></span>  
  
- <span data-ttu-id="f14a9-120">레지스트리 키가 읽기 전용인 경우</span><span class="sxs-lookup"><span data-stu-id="f14a9-120">The registry key is read-only.</span></span>  
  
## <a name="net-security"></a><span data-ttu-id="f14a9-121">.NET 보안</span><span class="sxs-lookup"><span data-stu-id="f14a9-121">.NET Security</span></span>  
 <span data-ttu-id="f14a9-122">로컬 컴퓨터(`Microsoft.Win32.Registry.LocalMachine`)보다 사용자 폴더(`Microsoft.Win32.Registry.CurrentUser`)에 데이터를 쓰는 것이 더 안전합니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-122">It is more secure to write data to the user folder — `Microsoft.Win32.Registry.CurrentUser` — rather than to the local computer — `Microsoft.Win32.Registry.LocalMachine`.</span></span>  
  
 <span data-ttu-id="f14a9-123">레지스트리 값을 만들 때 해당 값이 이미 있는 경우 수행할 작업을 결정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-123">When you create a registry value, you need to decide what to do if that value already exists.</span></span> <span data-ttu-id="f14a9-124">다른 악성 프로세스에서 값을 이미 만들고 액세스했을 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-124">Another process, perhaps a malicious one, may have already created the value and have access to it.</span></span> <span data-ttu-id="f14a9-125">레지스트리 값에 데이터를 넣으면 다른 프로세스에서 해당 데이터를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-125">When you put data in the registry value, the data is available to the other process.</span></span> <span data-ttu-id="f14a9-126">이를 방지하려면 `Overload:Microsoft.Win32.RegistryKey.GetValue`</span><span class="sxs-lookup"><span data-stu-id="f14a9-126">To prevent this, use the.`Overload:Microsoft.Win32.RegistryKey.GetValue`</span></span> <span data-ttu-id="f14a9-127">메서드를 재정의합니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-127">method.</span></span> <span data-ttu-id="f14a9-128">키가 아직 없는 경우 null이 반환됩니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-128">It returns null if the key does not already exist.</span></span>  
  
 <span data-ttu-id="f14a9-129">레지스트리 키가 ACL(액세스 제어 목록)로 보호된 경우에도 암호 등을 레지스트리에 일반 텍스트로 저장하는 것은 안전하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="f14a9-129">It is not secure to store secrets, such as passwords, in the registry as plain text, even if the registry key is protected by access control lists (ACL).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f14a9-130">참조</span><span class="sxs-lookup"><span data-stu-id="f14a9-130">See also</span></span>

- <xref:System.IO?displayProperty=nameWithType>
- [<span data-ttu-id="f14a9-131">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="f14a9-131">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="f14a9-132">파일 시스템 및 레지스트리(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="f14a9-132">File System and the Registry (C# Programming Guide)</span></span>](./index.md)
- [<span data-ttu-id="f14a9-133">C#을 사용하여 레지스트리에서 읽기, 쓰기 및 삭제</span><span class="sxs-lookup"><span data-stu-id="f14a9-133">Read, write and delete from the registry with C#</span></span>](https://www.codeproject.com/Articles/3389/Read-write-and-delete-from-registry-with-C)
