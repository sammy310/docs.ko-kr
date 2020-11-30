---
ms.openlocfilehash: f6e4c3d5c5fd020562e48515554136e0f8b6785c
ms.sourcegitcommit: 0802ac583585110022beb6af8ea0b39188b77c43
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "96032499"
---
### <a name="data-protection-dataprotectionblobs-uses-new-azure-storage-apis"></a>데이터 보호: DataProtection.Blobs에서 새로운 Azure Storage API 사용

`Azure.Extensions.AspNetCore.DataProtection.Blobs`은 [Azure Storage 라이브러리](https://github.com/Azure/azure-storage-net)에 따라 달라집니다. 이러한 라이브러리는 해당 어셈블리, 패키지 및 네임 스페이스의 이름을 바꿨습니다. ASP.NET Core 3.0부터 `Azure.Extensions.AspNetCore.DataProtection.Blobs`는 새 `Azure.Storage.` 접두사가 지정된 API 및 패키지를 사용합니다.

Azure Storage API에 대한 질문은 <https://github.com/Azure/azure-storage-net>을 사용하세요. 이 문제에 대한 자세한 내용은 [dotnet/aspnetcore#19570](https://github.com/dotnet/aspnetcore/issues/19570)을 참조하세요.

#### <a name="version-introduced"></a>도입된 버전

3.0

#### <a name="old-behavior"></a>이전 동작

패키지는 `WindowsAzure.Storage` NuGet 패키지를 참조했습니다.
패키지는 `Microsoft.Azure.Storage.Blob` NuGet 패키지를 참조합니다.

#### <a name="new-behavior"></a>새 동작

패키지는 `Azure.Storage.Blob` NuGet 패키지를 참조합니다.

#### <a name="reason-for-change"></a>변경 이유

이 변경으로 인해 `Azure.Extensions.AspNetCore.DataProtection.Blobs`는 권장 Azure Storage 패키지로 마이그레이션할 수 있습니다.

#### <a name="recommended-action"></a>권장 조치

ASP.NET Core 3.0과 함께 이전 Azure Storage API를 계속 사용해야 하는 경우 [WindowsAzure.Storage](https://www.nuget.org/packages/WindowsAzure.Storage/) 또는 [Microsoft.Azure.Storage](https://www.nuget.org/packages/Microsoft.Azure.Storage.Blob/) 패키지에 직접 종속성을 추가합니다. 이 패키지는 새 `Azure.Storage` API와 함께 설치할 수 있습니다.

대부분의 경우 업그레이드는 새 네임스페이스를 사용하도록 `using` 문만 변경하면 됩니다.

```diff
- using Microsoft.WindowsAzure.Storage;
- using Microsoft.WindowsAzure.Storage.Blob;
- using Microsoft.Azure.Storage;
- using Microsoft.Azure.Storage.Blob;
+ using Azure.Storage;
+ using Azure.Storage.Blobs;
```

#### <a name="category"></a>범주

ASP.NET Core

#### <a name="affected-apis"></a>영향을 받는 API

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
