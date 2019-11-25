---
title: DLL을 로드하는 동안 오류가 발생했습니다.
ms.date: 07/20/2015
f1_keywords:
- vbrID48
ms.assetid: 4226cd1f-028c-477d-88a5-cb57f7e0cdc8
ms.openlocfilehash: 36452cc6ff03042939cd4066aef76129b5bb8f0a
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74329553"
---
# <a name="error-in-loading-dll-visual-basic"></a>DLL을 로드하는 동안 오류가 발생했습니다(Visual Basic).
A dynamic-link library (DLL) is a library specified in the `Lib` clause of a `Declare` statement. Possible causes for this error include:  
  
- The file is not DLL executable.  
  
- The file is not a Microsoft Windows DLL.  
  
- The DLL references another DLL that is not present.  
  
- The DLL or referenced DLL is not in a directory specified in the path.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
- If the file is a source-text file and therefore not DLL executable, it must be compiled and linked to a DLL-executable form.  
  
- If the file is not a Microsoft Windows DLL, obtain the Microsoft Windows equivalent.  
  
- If the DLL references another DLL that is not present, obtain the referenced DLL and make it available.  
  
- If the DLL or referenced DLL is not in a directory specified by the path, move the DLL to a referenced directory.  
  
## <a name="see-also"></a>참조

- [Declare 문](../../../visual-basic/language-reference/statements/declare-statement.md)
