<!doctype html>
<html lang="en">
<head>
	<style>
		div.trello-list {
			display:inline;
			border-radius:3px;
			float:left;
			background-color:rgb(219, 219, 219);
			font-family: 'Helvetica', Arial, Helvetica, sans-serif;
			font-size:15px;
			font-style:normal;
			font-weight:bold;
			margin:5px;
			padding:5px;
			width:15%;
			overflow:auto;
		}
		h4.trello-list-name {
			margin:0px;
			padding-top:5px;
			padding-left:5px;
			padding-right:5px;
			padding-bottom:0px;
		}
		ul.trello-cards {
			list-style-type:none;
			padding-left:5px;
			padding-right:5px;
			-webkit-margin-before:0px;
		}
		li.trello-card {
			list-style-type:none;
			display:block;
			clear:both;
			padding-bottom:4px;
			padding-left:8px;
			padding-right:8px;
			margin-top:6px;
			border-radius:3px;
			background-color:#ffffff;
			border-bottom-color: rgb(189, 189, 189);
			border-width:1px;
			font-weight: normal;
			font-size:14px;
			overflow: auto;

			-webkit-touch-callout: none;
			-webkit-user-select: none;
			-khtml-user-select: none;
			-moz-user-select: none;
			-ms-user-select: none;
			user-select: none;
		}
		li.trello-card:hover {
			cursor:pointer;
			background-color:#f2f2f2;
		}
		div.trello-card-title {
			padding-top:6px;
			margin-bottom:4px;
		}
		div.trello-members {
			display:block;
			float:right;
			margin-top:10px;
		}
		div.trello-members img {
			margin-right:5px;
		}
		div.trello-checklists {
			display:none;
			clear:both;
			position:fixed;
			margin: 0 auto;
			top:10%;
			left:20%;
			right:20%;
			bottom:20%;
			border-radius: 5px;
			padding:12px;
			background-color:rgba(200,200,200,0.9);
			z-index:1000;
		}
		div.trello-checklist {
			clear:both;
		}
		div.trello-checklist-title {
			font-weight:bold;
			margin-top:7px;
			margin-bottom:5px;
		}
		div.trello-item {
			display:block;
		    margin-left:18px;
		}
		div.trello-item input[type="checkbox"] {
			margin-left:-18px;
		}
		div.badges {
			float:left;
			padding-bottom:2px;
		}
		div.badge {
			color: #b3b3b3;
			float: left;
			height: 18px;
			margin: 0 3px 3px 0;
			padding: 0 4px 0 0;
			position: relative;
			text-decoration: none;
		}
		span.badge-text {
			float: left;
			font-size: 12px;
			margin-top:5px;
		}
		span.trello-item-complete {
			color:#FFF;
			background-color:#24A828;
			border-radius:3px;
			padding:3px;
		}
		div.trello-clearfix:after {
			clear: both;
			content: ".";
			display: block;
			height: 0;
			overflow: hidden;
			visibility: hidden;
		}
		div.trello-card-labels {
			margin 0 8px;
			position:relative;
			z-index:30;
		}
		span.trello-card-label {
			border-radius: 0;
			float: left;
			height: 4px;
			margin-bottom: 1px;
			padding: 0;
			width: 40px;
			line-height: 100px;
		}
		.trello-card-label-green {
			background-color: rgb(52,178,125);
		}
		.trello-card-label-blue {
			background-color: rgb(77,119,203);
		}
		.trello-card-label-red {
			background-color: rgb(203,77,77);
		}
		.trello-card-label-orange {
			background-color: rgb(224,153,82);
		}
		.trello-card-label-purple {
			background-color: rgb(153,51,204);
		}
		.trello-card-label-yellow {
			background-color: rgb(219,219,87);
		}
		div.trello-legends {
			position:relative;
			display:inline;
			float:left;
			overflow:visible;
			height:100%;
			margin-left:5px;
		}
		a.trello-legend {
			display:block;
			width:100%;
			border-radius:3px;
			font-family: 'Helvetica', Arial, Helvetica, sans-serif;
			font-size:14px;
			font-style:normal;
			font-weight:bold;
			padding:5px;
			margin-top:5px;
			margin-left:5px;
			color:#fff !important;
			text-shadow:0 1px 2px rgba(0,0,0,0.6);
			text-decoration:none !important;
		}
		a.trello-legend:hover {
			cursor:pointer;
		}
		a.trello-legen-transparent {
			opacity:0.5;
		}
		span.trello-legend-count {
			float:right;
		}
	</style>
</head>

<body>
    <div id="output"></div>
    <script src="http://code.jquery.com/jquery-1.7.1.min.js"></script>
    <script src="https://api.trello.com/1/client.js?key=<?php echo trelloKey; ?>&token=<?php echo trelloToken; ?>"></script>
    <script>
        var    onLoadTrello = (function($, trello) {
            return function(trello, params) {
                var $output = $('#output'),
                    board_id = params.board_id,
                    divArray = [],
                    memberObj = {},
                    checklistObj = {},
                    listArray = [],
                    avatars = [],
                    clArray = [],
                    iArray = [],
                    badgeArray = [],
                    labelArray = [],
                    labelBigArray = [],
                    isChecked = '',
                    checklistArray = [],
                    labelNames = [],
                    legendArray = [],
                    countLegendObj = {},
                    itemCompleted = 0,
                    itemAll = 0,
                    completeClass;

                $.when(

                    // Get all members for the board (key: member id, value: member obj)
                    trello.get('boards/'+board_id+'/members', {fields:'avatarHash,fullName,username'}, function(members) {
                        $.each(members, function(mx,member) {
                            memberObj[member.id] = member;
                        });
                    }),

                    // Get all checklists for the board. (key: checklist id, value: array of checklist obj)
                    trello.get('boards/'+board_id+'/checklists', function(checklists) {
                        $.each(checklists, function(clx,checklist) {
                            if (!checklistObj.hasOwnProperty(checklist.idCard)) {
                                checklistObj[checklist.idCard] = [];
                            }
                            checklistObj[checklist.idCard].push(checklist);
                        })
                    }),

                    // Get all lists for the board.
                    trello.get('boards/'+board_id+'/lists', {cards:'open', card_fields:'idMembers,name,labels'}, function(lists) {
                        listArray = lists;
                    }),

                    // Get master label list.
                    trello.boards.get(board_id,function(data) {
                        labelNames = data.labelNames;
                    })

                ).then(function() {

                        $.each(listArray, function(lx,list) {
                            divArray.push('<div class="trello-list">');
                            divArray.push('<h4 class="trello-list-name">'+list.name+'</h4>');
                            divArray.push('<ul class="trello-cards">');

                            $.each(list.cards, function(cx, card) {

                                // Create avatar photo array.
                                avatars = [];
                                $.each(card.idMembers,function(mx,idMember) {
                                    var m = memberObj[idMember],
                                        avatarName = m['fullName']+' ('+m['username']+')';
                                    avatars.push('<img src="https://trello-avatars.s3.amazonaws.com/'+m['avatarHash']+'/30.png" width="30" height="30" alt="'+avatarName+'" title="'+avatarName+'">')
                                });

                                // Get the label name(s).
                                labelArray = [];
                                labelBigArray = [];
                                if (card.labels.length > 0){
                                    labelArray.push('<div class="trello-card-labels trello-clearfix">');
                                    labelBigArray.push('<div class="trello-legends" style="height:auto;margin-top:17px">');
                                    $.each(card.labels, function(lbx,label) {
                                        var color = label.color,
                                            name = label.name;
                                        labelArray.push('<span class="trello-card-label trello-card-label-'+color+'"></span>');
                                        labelBigArray.push('<a class="trello-legend trello-card-label-'+color+'" style="display:inline;">'+name+'</a>');
                                        if (!countLegendObj.hasOwnProperty(color)) {
                                            countLegendObj[color] = 0;
                                        }
                                        countLegendObj[color]++;
                                    });
                                    labelArray.push('</div>');
                                    labelBigArray.push('</div>');
                                }
    
                                clArray = [''];
                                clArray.push('<div class="trello-checklists">');
                                clArray.push('<h1>'+card.name+'</h1>');
                                clArray.push('<div class="trello-members" style="float:left;">'+avatars.join('')+'</div>');
                                clArray.push(labelBigArray.join(''));

                                badgeArray = [];
                                if (checklistObj.hasOwnProperty(card.id)) {
                                    // Get a checklist array for this card.
                                    checklistArray = checklistObj[card.id];
                                    if (typeof checklistArray === 'string') {
                                        checklistArray = [checklistArray];
                                    }

                                    itemCompleted = 0;
                                    itemAll = 0;

                                    $.each(checklistArray, function(clx, checklist) {
                                        
                                        // Create checklist items array.
                                        iArray = [];
                                        $.each(checklist.checkItems, function(clx, item) {
                                            itemAll++;
                                            if (item.state === 'complete') {
                                                isChecked = 'checked';
                                                itemCompleted++;
                                            } else {
                                                isChecked = '';
                                            }
                                            iArray.push('<div class="trello-item trello-item-'+item.state+'"><input type="checkbox" '+isChecked+' disabled>'+item.name+'</div>');
                                        });

                                        clArray.push('<div class="trello-checklist"><div class="trello-checklist-title">'+checklist.name+'</div>'+iArray.join('')+'</div>');
                                    });

                                    // Create badge area.
                                    badgeArray.push('<div class="badges">');
                                    completeClass = (itemCompleted === itemAll)? ' trello-item-complete': '';
                                    badgeArray.push('<div class="badge"><span class="badge-text'+completeClass+'">'+itemCompleted+'/'+itemAll+'</span></div>');
                                    badgeArray.push('</div>');
                                }
                                clArray.push('</div>');

                                divArray.push('<li class="trello-card">'+labelArray.join('')+'<div class="trello-card-title">'+card.name+'</div>'+badgeArray.join('')+'<div class="trello-members">'+avatars.join('')+'</div>'+clArray.join('')+'</li>');
                            });
                            divArray.push('</ul>');
                            divArray.push('</div>');
                        });

                        // Add Legends
                        if (labelNames) {
                            divArray.push('<div class="trello-legends">');
                            $.each(labelNames,function(color,name){
                                divArray.push('<a href="#" id="trello-card-label-'+color+'" class="trello-legend trello-card-label-'+color+'">'+((name)?name:'noname')+'&nbsp;<span class="trello-legend-count">'+(countLegendObj[color]?countLegendObj[color]:'0')+'</span></a>');
                            });
                            divArray.push('</div>');
                        }
    

                        $output.html(divArray.join(''));

                        $('.trello-card').on('click', function(e) {
                            $(this).find('.trello-checklists').toggle();
                            return false;
                        });

                        $('a.trello-legend').on('click',function(e) {
                            var $me = $(this),
                                color_class = $me.prop('id');
                            $('span.'+color_class).parent().parent().toggle();
                            $me.toggleClass('trello-legen-transparent');
                            return false;
                        });
                });
            };
        })(jQuery, Trello);

        onLoadTrello(Trello, {
            board_id: '<?php echo trelloBoardId; ?>'
        });

    </script>
</body>
</html>
