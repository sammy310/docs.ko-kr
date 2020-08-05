---
title: 가장 및 되돌리기
ms.date: 07/15/2020
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- WindowsIdentity objects, impersonating
- security [.NET], impersonating Windows accounts
- impersonating Windows accounts
ms.assetid: b93d402c-6c28-4f50-b2bc-d9607dc3e470
ms.openlocfilehash: 7eecc7d6cb3fa4cc1c1bd971d36f9d3ca47a7144
ms.sourcegitcommit: b7a8b09828bab4e90f66af8d495ecd7024c45042
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87555679"
---
# <a name="impersonating-and-reverting"></a>가장 및 되돌리기

> [!NOTE]
> 이 문서는 Windows에 적용 됩니다.
>
> ASP.NET Core에 대 한 자세한 내용은 [ASP.NET Core 보안](/aspnet/core/security/)을 참조 하세요.

Windows 계정을 가장하기 위해 Windows 계정 토큰을 가져와야 하는 경우도 있습니다. 예를 들어 ASP.NET 기반 애플리케이션이 여러 사용자를 대신하여 작동해야 하는 경우가 있습니다. 애플리케이션이 인터넷 정보 서비스(IIS)에서 관리자를 나타내는 토큰을 수락하고, 사용자를 가장하고, 작업을 수행하며, 이전 ID로 되돌릴 수 있습니다. 그런 다음 응용 프로그램은 권한이 적은 사용자를 나타내는 IIS의 토큰을 수락하고, 일부 작업을 수행하여, 다시 되돌릴 수 있습니다.  
  
 애플리케이션이 IIS에 의해 현재 스레드에 연결되지 않은 Windows 계정을 가장해야 하는 경우에는 해당 계정의 토큰을 검색하고 이 토큰을 사용하여 계정을 활성화해야 합니다. 이렇게 하려면 다음과 같은 작업을 수행합니다.  
  
1. 비관리 **LogonUser** 메서드를 호출하여 특정 사용자에 대한 계정 토큰을 검색합니다. 이 메서드는 .NET 기본 클래스 라이브러리에 없지만 관리 되지 않는 **advapi32.dll**에 있습니다. 비관리 코드에서 메서드에 액세스하는 작업은 고급 작업이므로 이 문서에서는 다루지 않습니다. 자세한 내용은 [비관리 코드 상호 운용](../../framework/interop/index.md)을 참조하세요. **LogonUser** 메서드 및 **advapi32.dll**에 대한 자세한 내용은 플랫폼 SDK 설명서를 참조하세요.  
  
2. 토큰을 전달하는 **WindowsIdentity** 클래스의 새 인스턴스를 만듭니다. 다음 코드는 `hToken`이 Windows 토큰을 나타내는 호출을 보여줍니다.  
  
    ```csharp  
    WindowsIdentity impersonatedIdentity = new WindowsIdentity(hToken);  
    ```  
  
    ```vb  
    Dim impersonatedIdentity As New WindowsIdentity(hToken)  
    ```  
  
3. 다음 코드에서와 같이, <xref:System.Security.Principal.WindowsImpersonationContext> 클래스의 새 인스턴스를 만들고 초기화된 클래스의 <xref:System.Security.Principal.WindowsIdentity.Impersonate%2A?displayProperty=nameWithType> 메서드로 이 인스턴스를 초기화하여 가장을 시작합니다.  
  
    ```csharp  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate();  
    ```  
  
    ```vb  
    WindowsImpersonationContext myImpersonation = impersonatedIdentity.Impersonate()  
    ```  
  
4. 더 이상 가장할 필요가 없으면, 다음 코드에서와 같이 <xref:System.Security.Principal.WindowsImpersonationContext.Undo%2A?displayProperty=nameWithType> 메서드를 호출하여 가장을 되돌립니다.  
  
    ```csharp  
    myImpersonation.Undo();  
    ```  
  
    ```vb  
    myImpersonation.Undo()  
    ```  
  
 신뢰할 수 있는 코드가 개체를 스레드에 이미 연결한 경우 <xref:System.Security.Principal.WindowsPrincipal> 계정 토큰을 사용 하지 않는 인스턴스 메서드 **Impersonate**를 호출할 수 있습니다. 이 기능은 스레드의 **WindowsPrincipal** 개체가 프로세스를 현재 실행 중인 사용자가 아닌 다른 사용자를 나타낼 때 유용합니다. 예를 들어, Windows 인증을 사용 설정하고 가장을 해제하여 ASP.NET을 사용할 때 이러한 상황이 발생할 수 있습니다. 이 경우, 프로세스는 인터넷 정보 서비스(IIS)에 구성된 계정에서 실행되는 반면 현재 보안 주체는 페이지에 액세스하는 Windows 사용자를 나타냅니다.  
  
 **Impersonate** 또는 **Undo** 는 현재 호출 컨텍스트와 연결 된 **Principal** 개체 ()를 변경 하지 않습니다 <xref:System.Security.Principal.IPrincipal> . 대신, 가장 및 되돌리기는 현재 운영 체제 프로세스와 연결 된 토큰을 변경 합니다.  
  
## <a name="see-also"></a>참고 항목

- <xref:System.Security.Principal.WindowsIdentity>
- <xref:System.Security.Principal.WindowsImpersonationContext>
- [Principal 개체 및 Identity 개체](principal-and-identity-objects.md)
- [비관리 코드와의 상호 운용](../../framework/interop/index.md)
- [ASP.NET Core 보안](/aspnet/core/security/)
