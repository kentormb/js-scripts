* Calculate the distance in meters between two coordinates 

var rad=function(x){return x*Math.PI / 180;};
var getDistance=function(p1,p2){var R=6378137;var dLat=rad(p2['lat']-p1['lat']);var dLong=rad(p2['lng']-p1['lng']);var a=Math.sin(dLat / 2)*Math.sin(dLat / 2)+
Math.cos(rad(p1['lat']))*Math.cos(rad(p2['lat']))*Math.sin(dLong / 2)*Math.sin(dLong / 2);var c=2*Math.atan2(Math.sqrt(a),Math.sqrt(1-a));var d=R*c;return d;};

* Get current c2o emmition

const final_number = () => {
   const c2o_emmition = 91594260;
   const c2o_per_10_sec = 3.5;
   const first_timestamp = 1604331900;
   let now = new Date;
   let utc_timestamp = Date.UTC(now.getFullYear(),now.getMonth(), now.getDate() , 
      now.getHours(), now.getMinutes(), now.getSeconds(), now.getMilliseconds());
   // timestamp in sec
   utc_timestamp = (utc_timestamp / 1000).toFixed();
   // how many 10 seconds since first timestamp
   let secondes_past = (first_timestamp - utc_timestamp) / 10;
   // current c2o emmition
   return (c2o_emmition + (secondes_past*c2o_per_10_sec)).toFixed(1)
}
