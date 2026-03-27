    async function getTronWeb() {
      let tronWeb;
      if (window.tronLink.ready) {
        tronWeb = tronLink.tronWeb;
      } else {
        const res = await tronLink.request({ method: 'tron_requestAccounts' });
        if (res.code === 200) {
          tronWeb = tronLink.tronWeb;
        }
      }
      return tronWeb;
    }
