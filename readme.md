1 , der 转 r，s
     let lenR = sign1[3];             
     let  r = sign1.slice(4, 4 + lenR);
     let  s = sign1.slice(6 + lenR);
     r = BigInteger.fromDERInteger(r).toBuffer(32);
     s = BigInteger.fromDERInteger(s).toBuffer(32);
     sign1Hex = Buffer.concat([r, s], r.length + s.length).toString('hex');

2, 压缩转非压缩     let Q = ecurve.Point.decodeFrom(SECP256K1,new Buffer(yzprdkey,'hex' ));   Q.getEncoded(false).toString('hex')
3，hex 转 Arrary
function buf2hex(buffer) {
  return Array.prototype.map.call(new Uint8Array(buffer), x => ('00' + x.toString(16)).slice(-2)).join('');
}   