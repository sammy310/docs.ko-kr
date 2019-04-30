---
title: "'Object' 형식의 인수를 사용하는 경우 'FilePut' 대신 'FilePutObject'를 사용하세요."
ms.date: 07/20/2015
f1_keywords:
- vbrUseFilePutObject
ms.assetid: d207b9b7-5898-4c13-8b03-9feefac5f726
ms.openlocfilehash: 3d793151905c61ee12eccdfdb5e9567a4924bb35
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62022521"
---
# <a name="use-fileputobject-instead-of-fileput-when-using-argument-of-type-object"></a>'Object' 형식의 인수를 사용하는 경우 'FilePut' 대신 'FilePutObject'를 사용하세요.
`FilePut` 메서드는 `Object`형식의 인수를 포함합니다. 모호성을 피하기 위해`FilePutObject` 대신 `FilePut` 를 사용해야 합니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- `FilePut` 을 `FilePutObject`로 바꿉니다.  
  
- `Object` 인수를 더 구체적인 형식으로 캐스트합니다.  
  
- `My.Computer.FileSystem` 개체에서 사용할 수 있는 기능을 사용합니다.  
  
## <a name="see-also"></a>참고자료

- [My.Computer.FileSystem](xref:Microsoft.VisualBasic.FileIO.FileSystem)
- [My.Computer.FileSystem.WriteAllBytes](xref:Microsoft.VisualBasic.MyServices.FileSystemProxy.WriteAllBytes%2A)
