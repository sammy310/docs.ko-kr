---
description: '자세한 정보: 방법: 그룹 연결에 사용자 정보 할당'
title: '방법: 그룹 연결에 사용자 정보 할당'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 7ce550d6-8f7c-4ea7-add8-5bc27a7b51be
ms.openlocfilehash: 2af901b91c561f5f46c63ed627cbd0053d30e624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99729265"
---
# <a name="how-to-assign-user-information-to-group-connections"></a><span data-ttu-id="6f15c-103">방법: 그룹 연결에 사용자 정보 할당</span><span class="sxs-lookup"><span data-stu-id="6f15c-103">How to: Assign User Information to Group Connections</span></span>

 <span data-ttu-id="6f15c-104">다음 예제에서는 이 코드 섹션이 호출되기 전에 애플리케이션이 *UserName*, *SecurelyStoredPassword* 및 *Domain* 변수를 설정하고 *UserName* 이 고유하다고 가정하여 사용자 정보를 그룹 연결에 할당하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="6f15c-104">The following example demonstrates how to assign user information to group connections, assuming that the application sets the variables *UserName*, *SecurelyStoredPassword*, and *Domain* before this section of code is called and that *UserName* is unique.</span></span>  
  
### <a name="to-assign-user-information-to-a-group-connection"></a><span data-ttu-id="6f15c-105">그룹 연결에 사용자 정보를 할당하려면</span><span class="sxs-lookup"><span data-stu-id="6f15c-105">To assign user information to a group connection</span></span>  
  
1. <span data-ttu-id="6f15c-106">연결 그룹 이름을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f15c-106">Create a connection group name.</span></span>  
  
    ```csharp  
    SHA1Managed Sha1 = new SHA1Managed();  
    Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
    String secureGroupName = Encoding.Default.GetString(updHash);  
    ```  
  
    ```vb  
    Dim Sha1 As New SHA1Managed()  
    Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
    Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
    ```  
  
2. <span data-ttu-id="6f15c-107">특정 URL에 대한 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f15c-107">Create a request for a specific URL.</span></span> <span data-ttu-id="6f15c-108">예를 들어 다음 코드는 URL `http://www.contoso.com.`에 대한 요청을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="6f15c-108">For example, the following code creates a request for the URL `http://www.contoso.com.`</span></span>  
  
    ```csharp  
    WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
    ```  
  
    ```vb  
    Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
    ```  
  
3. <span data-ttu-id="6f15c-109">웹 요청에 대한 자격 증명 및 연결 그룹 이름을 설정하고 **GetResponse** 를 호출하여 **WebResponse** 개체를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="6f15c-109">Set the credentials and Connection GroupName for the Web request, and call **GetResponse** to retrieve a **WebResponse** object.</span></span>  
  
    ```csharp  
    myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);
    myWebRequest.ConnectionGroupName = secureGroupName;  
  
    WebResponse myWebResponse=myWebRequest.GetResponse();  
    ```  
  
    ```vb  
    myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
    myWebRequest.ConnectionGroupName = secureGroupName  
  
    Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
    ```  
  
4. <span data-ttu-id="6f15c-110">WebRespose 개체를 사용한 후 응답 스트림을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="6f15c-110">Close the response stream after using the WebRespose object.</span></span>  
  
    ```csharp  
    MyWebResponse.Close();  
    ```  
  
    ```vb  
    MyWebResponse.Close()  
    ```  
  
 <span data-ttu-id="6f15c-111">예제</span><span class="sxs-lookup"><span data-stu-id="6f15c-111">Example</span></span>  
  
```csharp  
// Create a connection group name.  
SHA1Managed Sha1 = new SHA1Managed();  
Byte[] updHash = Sha1.ComputeHash(Encoding.UTF8.GetBytes(UserName + SecurelyStoredPassword + Domain));  
String secureGroupName = Encoding.Default.GetString(updHash);  
  
// Create a request for a specific URL.  
WebRequest myWebRequest=WebRequest.Create("http://www.contoso.com");  
  
myWebRequest.Credentials = new NetworkCredential(UserName, SecurelyStoredPassword, Domain);
myWebRequest.ConnectionGroupName = secureGroupName;  
  
WebResponse myWebResponse=myWebRequest.GetResponse();  
  
// Insert the code that uses myWebResponse.  
  
MyWebResponse.Close();  
```  
  
```vb  
' Create a secure group name.  
Dim Sha1 As New SHA1Managed()  
Dim updHash As [Byte]() = Sha1.ComputeHash(Encoding.UTF8.GetBytes((UserName + SecurelyStoredPassword + Domain)))  
Dim secureGroupName As [String] = Encoding.Default.GetString(updHash)  
  
' Create a request for a specific URL.  
Dim myWebRequest As WebRequest = WebRequest.Create("http://www.contoso.com")  
  
myWebRequest.Credentials = New NetworkCredential(UserName, SecurelyStoredPassword, Domain)  
myWebRequest.ConnectionGroupName = secureGroupName  
  
Dim myWebResponse As WebResponse = myWebRequest.GetResponse()  
  
' Insert the code that uses myWebResponse.  
MyWebResponse.Close()  
```  
  
## <a name="see-also"></a><span data-ttu-id="6f15c-112">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6f15c-112">See also</span></span>

- [<span data-ttu-id="6f15c-113">연결 관리</span><span class="sxs-lookup"><span data-stu-id="6f15c-113">Managing Connections</span></span>](managing-connections.md)
- [<span data-ttu-id="6f15c-114">연결 그룹화</span><span class="sxs-lookup"><span data-stu-id="6f15c-114">Connection Grouping</span></span>](connection-grouping.md)
